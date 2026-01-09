---
title: Game Selection & Authorization
deprecated: false
hidden: true
metadata:
  robots: index
---
## Game Launch & Session Creation

### Purpose

Create a secure session for a player to launch and play a specific game.

***

### Player Chooses Game

**Flow:** Player → Operator UI

The player selects a game from the Operator’s casino lobby.

***

### Operator Creates Session Token

The Operator generates a **session token** containing the following information:

* `playerId`
* `tenantCode`
* `currency`
* `mode` (`real` / `demo`)

This token uniquely represents a player session and is used during game authorization.

***

### Build Game Launch URL

The Operator constructs the game launch URL using the session token.

game_url?
t=tenantCode
&g=gameCode
&s=sessionToken
&l=language

***

### Redirect / iFrame Load

**Flow:** Operator → Player Browser

* The game client is loaded via redirect or iFrame
* Communication between the game client and RGS begins

***

## Player Authorization (Game Start)

### Purpose

Ensure that only valid and authorized players are allowed to start gameplay.

***

### Authenticate Session

**Flow:** Player → RGS → Wallet

RGS validates the session by calling the Operator’s Wallet service.

POST /api/v1/authenticate

**Example Request**

```curl
curl --location 'https://dev-demo-operator.kerma.games/api/v1/authenticate' \
--header 'Content-Type: application/json' \
--data '{
  "token": "cmiyr3ti8000201kh6i8oadwq"
}'
```

### Error Codes

<br />

### Wallet Validation Checks

The Wallet performs the following validations during player authorization:

| Validation Area                  | Error Code(s)  | Description                         |
| -------------------------------- | -------------- | ----------------------------------- |
| Token validity                   | `1200`         | Invalid player token                |
| Session validity                 | `1201`         | Invalid player session              |
| Player status (locked / blocked) | `1202`, `1207` | Player is locked or blocked         |
| Wallet status                    | `1208`         | Wallet blocked                      |
| Tenant mapping and status        | `1002`, `1003` | Tenant not found or tenant disabled |

**Authorization Result**

Success Response

```
{
  "status": "OK"
}
```

Failure Behavior

If authorization fails, the game is blocked and an error response is returned using one of the defined error codes, for example:

```
{
  "errorCode": 1207,
  "message": "Player blocked"
}
```
