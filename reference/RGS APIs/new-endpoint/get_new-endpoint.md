---
title: Game List
excerpt: >-
  This endpoint returns the list of slot games available to the client along
  with their core configuration details.
api:
  file: game-list.json
  operationId: get_new-endpoint
hidden: true
---
The response includes only games that are currently active and accessible. Each game provides essential information such as its name, code, status, URLs, RTP, betting configuration, and win limits. This data can be used to display available games, configure game launches, and determine supported betting parameters.
