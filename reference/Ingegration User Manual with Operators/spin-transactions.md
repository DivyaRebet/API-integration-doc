---
title: Spin Transactions
deprecated: false
hidden: true
metadata:
  robots: index
---
## Spin / Wager Execution (Transaction Flow)

### Purpose

Process a single spin atomically.

***

### &#x20;Player Presses Spin

**Game Client → RGS**

***

### RGS Internal Validations

* Session valid
* Security Middleware Checks
* Game active
* Bet allowed or not
* Currency allowed or not

***

## Wallet Transaction (Debit)

**RGS → Wallet**

```
POST /api/v1/transactions
curl --location 'https://api.youroperator.com/wallet/api/v1/transactions' \
--header 'Content-Type: application/json' \
--data '{
    "token": "01KE6MCVQT0GHV8331NGDH69PS",
    "gameId": "xxx",
    "gameCode": "pay-day",
    "betId": "xxx",
    "betAmount": 1,
    "winAmount": 2,
    "isEndRound": true,
    "betType": "NORMAL",
    "currency": "USD",
    "transactionId": "xxx",
    "created": "x",
    "updated": "x",
    "walletType": "CASH"
}'

RESPONSE
{
   "balance": "10000001",
   "currency": "USD",
   "transactionId": "01KE6MD30B6N5R0TVEE5HXAK16"
}

```

***

### Wallet Response

### Enough Balance

```json
{"balance":115.50}
```

### Insufficient Balance

```json
{"code":1301,"message":"Insufficient balance"}
```
