---
name: eliq-present-energy-insights
description: Read Eliq Insights for one household — consumption, cost, appliance breakdown, similar homes, market prices, forecast and advice — and present it to an end user.
api: Eliq Insights API
generated: '2026-09-06'
method: generated
source: https://developer.eliq.com/doc/energy-insights-for-businesses, https://developer.eliq.com/doc/date-and-time, openapi/eliq-insights-api-openapi.yaml
base_url: https://eliq.insights-api.eliq.com
operations:
  - post-oauth-token
  - get-v3-locations-locationExtref
  - get--v3-users-userId-locations
  - get-v3-locations-locationId
  - get-v3-locations-locationId-consumption
  - get-v3-locations-locationId-euc
  - get-v3-locations-locationId-similarhomes
  - get-v3-locations-locationId-marketprice-prices
  - get-v3-locations-locationId-marketprice-price-summary
  - get-v3-locations-locationId-forecast
  - get-v3-location-anomalies
  - get-v3-location-advice
  - get-v3-locations-locationId-budgets
  - get-v3-location-profile-completion
  - get-v3-heartbeat
---

# Present Eliq insights to an end user

The Insights API is the read side. Data goes in through the Data Management API; this is what
comes out, already shaped for a UI.

## 1. Get a delegated token

Insights enforces user context, so mint a token **for the user**, not just for your app:

```json
{ "grant_type": "client_credentials",
  "client_id": "<client_id>", "client_secret": "<client_secret>",
  "aud": "insights-api", "scope": "insights.read",
  "sub": "<user_id>", "sub_type": "user" }
```

Add `"issue_refresh_token": true` if you want a refresh token (30 days) alongside the 1-hour
access token.

## 2. Resolve the location

`get--v3-users-userId-locations` for a user's locations, or
`get-v3-locations-locationExtref` (`GET /v3/locations`) to look one up by your own external
reference. `get-v3-locations-locationId` returns the location itself — which fuels it has and
what resolution its data supports. **Read this before requesting a chart**: asking for `30min`
data from a location that only holds daily values gets you nothing useful.

## 3. Read what you need

| What | Operation |
|---|---|
| Consumption / cost over a period | `get-v3-locations-locationId-consumption` |
| Appliance breakdown (NILM disaggregation) | `get-v3-locations-locationId-euc` |
| Peer comparison | `get-v3-locations-locationId-similarhomes` |
| Day-ahead market price + summary | `get-v3-locations-locationId-marketprice-prices`, `…-price-summary` |
| Forecast | `get-v3-locations-locationId-forecast` |
| Anomalies | `get-v3-location-anomalies` |
| Personalised advice | `get-v3-location-advice` |
| Budget status | `get-v3-locations-locationId-budgets` |

Most take `from`, `to`, `fuel`, `unit` (`energy` or `cost`) and `resolution`.

## 4. Things that will bite you

- **Times are local, not UTC.** The Insights API returns everything in the *location's* time
  zone, deliberately, so it is ready to render. The Data Management API is the opposite for
  high-resolution data (UTC). Do not mix them.
- **Cost needs a price formula.** If a period has no formula, Eliq returns energy and silently
  omits cost for that period. It is not an error.
- **Empty insights usually mean an empty profile.** Check
  `get-v3-location-profile-completion` before concluding a location has no EUC or similar-homes
  data.
- **Do not poll.** Insights resources should not be re-read more than once every 60 seconds
  unless they were just updated; cache user/location metadata for at least 24 hours. For
  availability use `get-v3-heartbeat` (`GET /v3/health/heart_beat`), never a functional endpoint.
- **The Home Profile surface is deprecated** in favour of the Location Profile
  (`get-v3-locations-locationId-homeprofile` and friends). Eliq gives 180 days from notice to
  migrate off a deprecated endpoint.
