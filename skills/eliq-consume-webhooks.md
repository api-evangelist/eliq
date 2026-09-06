---
name: eliq-consume-webhooks
description: Receive, verify and process Eliq webhook notifications — budgets, anomalies, market-price alerts, monthly insights and Eliq Connect status changes.
api: Eliq webhooks
generated: '2026-09-06'
method: generated
source: https://developer.eliq.com/doc/webhooks
operations: []
event_types:
  - budget_weekly
  - budget_monthly
  - daily_anomaly
  - monthly_anomaly
  - notifications_market_price_next_day_avg_price_alert
  - notifications_market_price_next_day_hour_price_alert
  - monthly_insight
  - connection_action_required
  - connection_first_data_received
---

# Consume Eliq webhooks

Eliq pushes events **to you**. You implement the endpoint; Eliq POSTs to it. There is no
webhook-management API — endpoints and the signing secret are configured with Eliq. You may
route every event type to one endpoint or split them across several.

## Verify the signature — before parsing anything

Every event carries:

```
X-Eliq-Signature: t=1591091590,sha256=<hex>
```

1. Take the `t=` value and the **raw** JSON body exactly as received.
2. Sign `"{timestamp}.{json_payload}"` with HMAC-SHA256 using the secret Eliq gave you.
3. Compare with the `sha256=` value, constant-time.

Re-serialising the body before signing will break this. Keep the raw bytes.

## Answer fast, and expect duplicates

- Return **2xx within 10 seconds**. Do the work asynchronously.
- Eliq retries with decreasing frequency until it gets a 2xx or **24 hours** elapse, generating
  a fresh timestamp and signature each time.
- Delivery is **at-least-once**. Store the `id` of every event you have processed and drop
  repeats. This is stated in Eliq's docs as a consumer obligation, not a nice-to-have.

## Envelope

```json
{ "id": "<uuid>", "created_date": "<ISO 8601 UTC>", "type": "notification_created",
  "object": { "location_id": 1234, "location_ext_ref": "<your ref>",
              "type": "<notification type>", "object": { } } }
```

Branch on the **inner** `type` — the outer one is `notification_created` for every notification.
The inner `object` shape varies per type; treat an unrecognised type as a no-op rather than an
error, so a new Eliq notification type does not take your endpoint down.

## The types, and what they mean

- `budget_weekly` / `budget_monthly` — a budget closed under or over its limit, or the forecast
  says it will be exceeded. Body mirrors the Insights budget object (`limit`, `status.value`,
  `status.forecast`, `status.result`).
- `daily_anomaly` / `monthly_anomaly` — yesterday's, or this month's, consumption is materially
  off expectation (`status.result` = `high`/`low`).
- `notifications_market_price_next_day_avg_price_alert` /
  `…_hour_price_alert` — next-day price alerts, generated at **17:00 Stockholm time**.
- `monthly_insight` — last month's summary, including localised `message.language.<locale>`
  header and content text you can render directly.
- `connection_action_required` — an Eliq Connect meter-data connection needs the end user to
  re-authorise.
- `connection_first_data_received` — a connection completed its first successful sync; safe to
  start showing data.

## Endpoint requirements

HTTPS is required. You may additionally protect the endpoint with Basic auth or OAuth 2.0 —
signature verification is on top of that, not instead of it.
