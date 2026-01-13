---
title: Rollback Cases
excerpt: To understand about rollback cases communication between RGS and Operator
deprecated: false
hidden: false
metadata:
  robots: index
---
## Error Handling & Rollback

### Purpose

Protect against financial inconsistency.

***

### Failure Scenarios

* Network timeout
* Wallet error
* Duplicate request

***

### Rollback Call

**RGS → Operator Wallet**

```
POST /api/v1/transactions (rollback=true)

```

**Wallet:**

* Reverts transaction
* Returns correct balance

***

## Recovery

**RGS:**

* Marks round failed in it's own system
* Prevents double play
* Supports reconnect

<br />

### Rollback Error Codes

The following error codes may be returned when processing a rollback request.

| Error Code | Description                     | When It Occurs                                                       |
| ---------: | ------------------------------- | -------------------------------------------------------------------- |
|     `2400` | Bet not found                   | Original bet transaction does not exist                              |
|     `2401` | Duplicate transaction           | Rollback request is sent more than once with the same transaction ID |
|     `2403` | Transaction already processed   | Transaction has already been finalized and cannot be rolled back     |
|     `2404` | Transaction already rolled back | Rollback was already successfully applied                            |
|     `2405` | Invalid rollback                | Rollback request is invalid or violates rollback rules               |
|     `2406` | Invalid transaction ID          | Transaction ID is missing or malformed                               |
|     `3000` | Internal server error           | Unexpected system error during rollback processing                   |

<br />