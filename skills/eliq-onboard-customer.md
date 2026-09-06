---
name: eliq-onboard-customer
description: Provision a utility customer in Eliq — user, location, location profile, meter and price formula — so Eliq can start producing insights for that household.
api: Eliq Data Management API
generated: '2026-09-06'
method: generated
source: https://developer.eliq.com/doc/step-by-step-guide-to-eliq-data-management-api, openapi/eliq-data-management-api-openapi.json
base_url: https://eliq.data-management-api.eliq.com/integration/api/v1
operations:
  - post-oauth-token
  - put-users-userId
  - put-locations-locationId
  - set-locations-locationId-profile-values
  - put-meter-meterid
  - add-or-update-meter-price-formulas
  - get-users-userId
  - delete-users-userId
---

# Onboard a customer into Eliq

Eliq's model is ordered: a **User** owns **Locations**, a Location holds **Meters**, a Meter
carries **energy data** and **price formulas**. Create them in that order — a location cannot be
created before its user exists.

## 1. Get a token

`post-oauth-token` — `POST https://auth-api.eliq.com/oauth/token`

```json
{ "grant_type": "client_credentials",
  "client_id": "<your client_id>",
  "client_secret": "<your client_secret>",
  "aud": "data-management-api" }
```

Send the returned `access_token` as `Authorization: Bearer <token>` on every call below. It is
valid for 3600 seconds. A `400` mid-session usually means it expired — mint a new one.

## 2. Create the user

`put-users-userId` — `PUT /users/{id}`. You choose `{id}`; Eliq returns it back with an
`eliq_id` it assigned. Because the id is yours, **this call is replayable**: running it twice
converges rather than creating two users.

## 3. Create the location

`put-locations-locationId` — `PUT /locations/{id}` with `user_id` in the body plus an `address`
(`country_code`, `postal_code`, `street_address`, `city`). Also replayable.

## 4. Add the location profile

`set-locations-locationId-profile-values` — `POST /locations/{locationId}/profile`.

Do not skip this. Energy Usage Categories, Similar Homes and customised advice are all computed
from profile data; without it those insights stay empty. Eliq recommends collecting the profile
during onboarding (the `location-profile-wizard-v1` web component exists for exactly this).

## 5. Create the meter

`put-meter-meterid` — `PUT /meters/{id}` with `fuel`, `location_id`, `user_id`,
`supply_start_date`, `type` (`import`/`export`) and `model`. If you get
`400 Invalid meter model`, ask your Eliq contact which model string your account uses — the
value is account-specific and cannot be guessed.

## 6. Add a price formula

`add-or-update-meter-price-formulas` — `POST /meters/{meterId}/priceformulas`. Without one Eliq
returns energy but not cost, and silently skips cost for any period a formula does not cover.
A formula is `currency_code` + `from`/`to` + `elements[]` (a `charge` at a resolution, and/or a
`unit_rate`). Formulas are per meter and per date range; you may hold several for one meter as
long as their ranges do not overlap.

## Rules that apply throughout

- **Errors**: `{ code, description, request_id }`. Log `request_id` (also `X-Request-Id`) —
  Eliq asks for it in support requests. Fix 4xx before retrying; back off exponentially on 5xx.
  Never retry blindly. See `errors/eliq-problem-types.yml`.
- **Idempotency**: only the `PUT` upserts above are replay-safe. `POST` price formulas and
  energy writes are not — do not fire them twice hoping for the same result.
- **Reversal**: `delete-users-userId`, `delete-locations-locationId`, `delete-meter-meterid`.
  No time window is published for any of them.
- **Volume**: past a handful of customers, stop using these singleton endpoints. Production
  loading must go through `/jobs` — see `eliq-bulk-load-energy-data`.
