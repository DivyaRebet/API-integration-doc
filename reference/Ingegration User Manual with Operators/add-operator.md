---
title: Operator Integration
excerpt: This demonstrates how we can add operator
deprecated: false
hidden: false
metadata:
  robots: index
---
## Add an operator (Commonly from our internal backoffice)

To register an operator we use back-office internally.

We can manually add an operator by using the API endpoint of our service entity and add specific parameters.

<br />

```curl
curl -X POST http://localhost:3000/tenants \
  -H "Content-Type: application/json" \
  -d '{
    "name": "Demo",
    "code": "KARMA123",
    "endpoint": "https://api.karmagames.io",
    "status": "ACTIVE",
    "integrationMode": "INHOUSE"
  }'
```

<br />

Next