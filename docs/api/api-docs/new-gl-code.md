# Add New GL Code

### Type of Request: `PUT`

### Description

### Endpoint
- Develop: `http://develop:6569/run/ecommerce/wsapi/enternewglcode?[params]`
- Production: `http://develop:6569/run/ecommerce/wsapi/enternewglcode?[params]`
- Example: `http://develop:6569/run/ecommerce/wsapi/enternewglcode?customerId=0013265`

### Available Parameters

| Parameter     | Required | Example        |
|---------------|----------|----------------|
|customerId     |True      |00013265        |

### Required Request Body (Example)
```
{
  "codes": [
    {
      "item": "123.45678.9",
      "code": "1234"
    }
  ]
}
```

### Expected Response

```
{
    "message": "Records Added: 0. Records Updated: 1. Records Deleted: 0."
}
```
OR
```
{
    "message": "Records Added: 1. Records Updated: 0. Records Deleted: 0."
}
```
OR
```
{
    "message": "Records Added: 0. Records Updated: 0. Records Deleted: 1."
}
```