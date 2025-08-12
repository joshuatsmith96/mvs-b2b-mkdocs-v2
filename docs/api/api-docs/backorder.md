# Backorder

### Type of Request: `GET`

### Description
Returns a list of orders and items currently on backorder.

### Endpoint

- Develop: `http://develop:6569/run/ecommerce/wsapi/boinquiry?[param]`
- Production: `http://mvet:6569/run/ecommerce/wsapi/boinquiry?[param]`
- Example: `http://develop:6569/run/ecommerce/wsapi/boinquiry?customer=0002789`

### Available Parameters

| Parameter     | Required | Example        |
|---------------|----------|----------------|
|customer       |True      |0002789         |

### Expected Response

```
[
    {
        "date": 20250731,
        "orderNumber": 45929940,
        "accountNumber": "0002789",
        "itemNumber": "350.81827.2",
        "description": "MUZZLE BASKERVILLE ULTRA SET/6",
        "backorderedQuantity": 1,
        "orderedQuantity": 1,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929940,
        "accountNumber": "0002789",
        "itemNumber": "653.54034.3",
        "description": "DERMOSCENT ATOP 7 HYDRA WIPES",
        "backorderedQuantity": 2,
        "orderedQuantity": 2,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929940,
        "accountNumber": "0002789",
        "itemNumber": "052.02110.3",
        "description": "AVENTI OMEGA 3 COMPLETE 500ml",
        "backorderedQuantity": 1,
        "orderedQuantity": 1,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929940,
        "accountNumber": "0002789",
        "itemNumber": "191.26115.3",
        "description": "BROMFENAC OPHTHALMIC SOLUTION",
        "backorderedQuantity": 1,
        "orderedQuantity": 1,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929940,
        "accountNumber": "0002789",
        "itemNumber": "000.06061.2",
        "description": "MVET WHITE POROUS TAPE 1\"",
        "backorderedQuantity": 3,
        "orderedQuantity": 3,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929940,
        "accountNumber": "0002789",
        "itemNumber": "000.02034.3",
        "description": "MVET SHOE COVERS XL",
        "backorderedQuantity": 1,
        "orderedQuantity": 1,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929940,
        "accountNumber": "0002789",
        "itemNumber": "261.91000.2",
        "description": "Vr BETTER GLOVES XL",
        "backorderedQuantity": 5,
        "orderedQuantity": 5,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929941,
        "accountNumber": "0002789",
        "itemNumber": "474.76127.3",
        "description": "ADAPTER PLUG YELLOW 1/4cc -",
        "backorderedQuantity": 1,
        "orderedQuantity": 1,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929941,
        "accountNumber": "0002789",
        "itemNumber": "474.50102.2",
        "description": "EMCARE BIOFREE FLUSH SOLUTION",
        "backorderedQuantity": 3,
        "orderedQuantity": 3,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929941,
        "accountNumber": "0002789",
        "itemNumber": "370.02555.3",
        "description": "ICHON STER PS-GAG 5X5ml SLEEVE",
        "backorderedQuantity": 1,
        "orderedQuantity": 1,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929941,
        "accountNumber": "0002789",
        "itemNumber": "350.19998.2",
        "description": "CALM CARRIER SLIDING CAT",
        "backorderedQuantity": 4,
        "orderedQuantity": 4,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929941,
        "accountNumber": "0002789",
        "itemNumber": "350.50343.2",
        "description": "BOWL ECON SS 16oz",
        "backorderedQuantity": 6,
        "orderedQuantity": 6,
        "shippedQuantity": 0
    },
    {
        "date": 20250731,
        "orderNumber": 45929941,
        "accountNumber": "0002789",
        "itemNumber": "377.12092.2",
        "description": "KONG GOODIE BONE MED",
        "backorderedQuantity": 3,
        "orderedQuantity": 3,
        "shippedQuantity": 0
    }
]
```