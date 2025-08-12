# Create Order

### Type Of Request: `POST`

### Description
This API creates a new order.

### Endpoint

Develop: `http://develop:6569/run/ecommerce/wsapi/order/create`

Production: `http://mvet:6569/run/ecommerce/wsapi/order/create`

### Required Body Request (Example)

```
{
  "orderTaker": "SYS",
  "customer": "0018698",
  "shipTo": "",
  "poNumber": "",
  "commerceOrderNumber": "",
  "freight": 0.75,
  "comments": "",
  "details": [
    {
      "itemNumber": "000.06060.2",
      "itemQuantity": 20,
      "sellPrice": 2,
      "discount": 0,
      "promoNumber": 0,
      "promoType": "promo type",
      "promoLine": "promo line",
      "promoFlag": "flag",
      "licenseNumber": "DEA123",
      "licenseType": "DVM",
      "licenseAuthority": "DEA"
    }
  ]
}
```

### Expected Response

```
{
    "orderNumber": 45958102,
    "orderStatus": "200",
    "errorText": ""
}
```