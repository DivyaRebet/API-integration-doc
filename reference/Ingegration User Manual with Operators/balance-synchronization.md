---
title: Balance Synchronization
excerpt: This is to demonstrate how can we fetch player balances from an Operator.
deprecated: false
hidden: true
metadata:
  robots: index
---
### Purpose

Keep RGS aware of the real wallet balance as multiple games are available on operator and user might have different balance than last request. We keep and update the balance.

<br />

### Balance Polling (Optional Loop)

**RGS → Wallet**

```
POST /api/v1/balance
curl --location 'https://api.wallet.com/api/v1/balance' \
--header 'Content-Type: application/json' \
--data '{
    "token": "cmjjtrgv90002zvyk2cre1k3a",
    "currency": "USD"
}'

```

**Response:**

```
{
   "balance": "10000000"
}
```

**Used for:**

* Initial UI
* Reconnects
* Safety checks

<br />