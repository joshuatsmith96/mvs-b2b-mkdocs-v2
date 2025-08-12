# Return Order

### Type of Request: `POST`

### Description
This API returns an order.

### Endpoint

Develop: `http://develop:6569/run/ecommerce/wsapi/order/return`

Production: `http://mvet:6569/run/ecommerce/wsapi/order/return`

### Required Body Request (Example)

```
{
  "customer": "0018698",
  "shipTo": "",
  "details": [
    {
      "itemNumber": "000.06060.2",
      "itemQuantity": 0,
      "sellPrice": 0,
      "discount": 5,
      "creditReason": "string",
      "creditCause": "string",
      "originalOrder": "",
      "originalBackOrder": 0
    }
  ]
}
```

### Expected Response

```
{
    "orderNumber": 45958103,
    "orderStatus": "200",
    "errorText": ""
}
```