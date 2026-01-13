---
title: Spin Transactions
deprecated: false
hidden: false
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
* Security Middlewares Checks
* Game active
* Bet allowed or not
* Currency allowed or not
* More checks

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
   "transactionId": "01KE6MD30B6N5R0TVEE5HXAK16" --via wallet
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

<br />

### Transaction Error Codes

The following error codes may be returned during bet, win, or rollback transactions.

| Error Code | Description                     | When It Occurs                                            |
| ---------: | ------------------------------- | --------------------------------------------------------- |
|     `1300` | Invalid bet amount              | Bet amount is outside allowed limits or malformed         |
|     `1301` | Insufficient balance            | Player balance is not enough to place the bet             |
|     `2400` | Bet not found                   | Referenced bet transaction does not exist                 |
|     `2401` | Duplicate transaction           | Same transaction ID is sent more than once                |
|     `2403` | Transaction already processed   | Transaction has already been completed                    |
|     `2404` | Transaction already rolled back | Rollback requested for an already rolled-back transaction |
|     `2405` | Invalid rollback                | Rollback request is invalid or inconsistent               |
|     `2406` | Invalid transaction ID          | Transaction ID format is invalid or missing               |
|     `3000` | Internal server error           | Unexpected system error during transaction processing     |