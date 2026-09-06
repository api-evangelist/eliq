---
name: eliq-bulk-load-energy-data
description: Load or delete energy, user, location and meter data in bulk through Eliq's asynchronous Jobs API, and reconcile a job that partially failed.
api: Eliq Data Management API
generated: '2026-09-06'
method: generated
source: https://developer.eliq.com/doc/jobs, https://developer.eliq.com/doc/eliq-api-guidelines, openapi/eliq-data-management-api-openapi.json
base_url: https://eliq.data-management-api.eliq.com/integration/api/v1
operations:
  - create-job
  - get-job
  - get-jobs
  - get-job-failures
  - get-job-result
  - cancel-job
---

# Bulk-load data into Eliq with Jobs

Eliq's API guidelines make this a **requirement**, not a preference: batch endpoints "must be
used instead of multiple single requests when loading data via the Data Management API in
production."

## Submit

`create-job` — `POST /jobs/{entity}/{operation}` as `multipart/form-data` with a single file
part named `content`.

- Format: **`.ndjson`** — one JSON object per line, `\n` separated. Nothing else is accepted.
- Maximum file size: **100 MB**.
- Entities: `user`, `location`, `meter`, `energy-period`, `energy-daily`,
  `energy-highres-{hour,30min,15min,6min}`, `homeprofile`, `locationprofile`, `priceformula`,
  `consent`, `euc`, `similar-homes-*`, `location-forecasts-*`, `insights-*`,
  `notification-history`.
- Operations: `upsert`, `delete`, `export` (not every pair exists — the supported matrix is on
  the Jobs page).
- Give each file a distinct name. Re-posting the same file under a new name to force
  reprocessing is an explicit guideline violation.

## Watch

`get-job` / `get-jobs`. States: `queued` → `processing` → `completed` | `failed`. A
`processing` job updates its handled-row count roughly every 30 seconds — use that to confirm
progress rather than polling harder. Status endpoints should not be polled more than once
every 5 seconds.

Jobs run **sequentially and in submission order**, so ordering dependencies across files hold
(users before locations). Ordering **inside** a file does not: two rows updating the same id
in one file can race. Keep ids unique within a file.

## Reconcile a failure

`failed` means one or more rows failed — and **successful rows are not rolled back**. There is
no transaction here. So:

1. `get-job-failures` — `GET /jobs/{jobId}/failures` returns each failing row index with the
   same `{ code, description }` codes the synchronous endpoints use.
2. Fix those rows only. Eliq retries a failed job up to three times on its own before moving on.
3. Expect cascades: a user that failed to import will take down a location in a later job.
4. A file with more than **1000** failing rows stops early and is marked `failed` — that is a
   formatting problem, not a data problem. Fix the file, do not resubmit it as-is.

## Cancel

`cancel-job` — `GET /jobs/{jobId}/cancel`. This is the reversal path, and it only works
**before the job finishes**; Eliq publishes no time bound. The guidelines ask that unnecessary
jobs be cancelled rather than left to process.

## Export

`export` operations write results you retrieve with `get-job-result`
(`GET /jobs/{jobId}/result`, paged at `/result/{page}`) — `application/x-ndjson`.
