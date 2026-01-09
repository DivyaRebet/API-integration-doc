---
title: Getting game
excerpt: This demonstrates how we get one particular game and it's launch
deprecated: false
hidden: true
metadata:
  robots: index
---
## Fetch Tenant-Specific Game Details

Fetch detailed, **tenant-specific configuration** for a given game using its `gameId`.

***

### Endpoint

`GET /gamelist/'tenantCode'/'gameId'`

### RGS Validation

Before returning the game details, RGS validates:

* Tenant is active
* Game is active
* Game is enabled for the specified tenant
* Supported currency for the tenant
* Supported platform (web, mobile, etc.)
* Supported language

***

### Response Includes

* Game metadata
* Bet limits
* Enabled features
* Tenant or version-specific overrides
