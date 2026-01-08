---
title: Add your operator
excerpt: This demonstrates how we can add operator
deprecated: false
hidden: true
metadata:
  robots: index
---
To register an operator we use backoffice internally.

We can manually add an operator by using the API endpoint of our service entity and add specific parameters.

<br />

```powershell
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

<br />
