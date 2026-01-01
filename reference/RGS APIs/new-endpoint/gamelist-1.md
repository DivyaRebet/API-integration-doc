---
title: Get Game List
excerpt: >-
  Retrieve a list of active games for a specific tenant, including
  configurations and metadata.
api:
  file: game-list.json
  operationId: gamelist
hidden: false
link:
  new_tab: false
---
## Get Game List

This API returns the list of active games available for a specific tenant, including game configurations and metadata for client display and selection.

### Endpoint

- **URL**: `/gamelist`
- **Method**: `GET`
- **Query Parameter**: `tenant` (string, required) - The tenant identifier, default is `kdemo`.

### Response

- **Status Code**: `200 OK`
- **Content-Type**: `application/json`

#### Response Schema

```json
{
  "games": [
    {
      "id": "string",
      "name": "string",
      "description": "string",
      "code": "string",
      "status": "number",
      "url": "string",
      "logicUrl": "string",
      "type": "number",
      "rtp": "string",
      "maxWin": "string",
      "baseBet": "string",
      "createdAt": "string",
      "updatedAt": "string"
    }
  ]
}
```

#### Example Response

```json
{
  "games": [
    {
      "id": "019b6913-e803-7051-9ba8-ccc0904dae5d",
      "name": "Pay Day",
      "description": "Pay Day",
      "code": "pay-day",
      "status": 0,
      "url": "https://example.com/super-fun-game",
      "logicUrl": "http://dev-logic-pay-day:5000",
      "type": 0,
      "rtp": "96.5",
      "maxWin": "100000",
      "baseBet": "1",
      "createdAt": "2025-12-29T07:47:50.916Z",
      "updatedAt": "2025-12-29T07:47:50.916Z"
    },
    {
      "id": "019b6913-e803-7051-9ba8-ca0f0e494898",
      "name": "Whisker Wars",
      "description": "Whiskers Wars",
      "code": "whisker-wars",
      "status": 0,
      "url": "https://example.com/super-fun-game",
      "logicUrl": "http://dev-logic-whisker-wars:5000",
      "type": 0,
      "rtp": "96.5",
      "maxWin": "100000",
      "baseBet": "1",
      "createdAt": "2025-12-29T07:47:50.916Z",
      "updatedAt": "2025-12-29T07:47:50.916Z"
    }
  ]
}
```

### Code Sample

```shell
curl --location "https://dev-rgs.kerma.games/gamelist?tenant=kdemo"
```

### Notes

- Ensure the `tenant` parameter is correctly set to retrieve the appropriate game list.
- The `status` field indicates the game's availability.

### What's Next?

Explore more endpoints and learn how to integrate them into your application. Check out our [API Reference](#) for additional details.