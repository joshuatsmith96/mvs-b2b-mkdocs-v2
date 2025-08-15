# Invoice Details

### Type of Request: `GET`

### Description
Get details for a given invoice number and customer.

### Endpoint

Develop: `http://develop:6569/run/ecommerce/wsapi/invoice/details?[params]`

Production: `http://mvet:6569/run/ecommerce/wsapi/invoice/details?[params]`

Example: `http://develop:6569/run/ecommerce/wsapi/invoice/details?invoiceNumber=22093640-000&customer=0018698`

### Available Parameters

| Parameter     | Required | Example        |
|---------------|----------|----------------|
|invoiceNumber  |true      |22093640-000    |
|customer       |true      |0018698         |

### Expected Response

```
{
    "orderType": "Invoiced",
    "returnable": true,
    "invoiceNumber": "22093640-000",
    "type": "Order",
    "invoiceDate": "05/01/2024",
    "shipVia": "",
    "warehouse": "MVS DALLAS",
    "terms": "NET 10TH",
    "address": {
        "shipping": {
            "line1": "3985 HIGHWAY 59",
            "line2": "DEVUN JOHN DVM",
            "line3": "",
            "city": "MANDEVILLE",
            "state": "LA",
            "zip": "704711958"
        },
        "billTo": {
            "line1": "3985 HIGHWAY 59",
            "line2": "DEVUN JOHN DVM",
            "line3": "",
            "city": "MANDEVILLE",
            "state": "LA",
            "zip": "704711958"
        }
    },
    "totalLineItems": 12,
    "totalShipQuantity": 21,
    "totalShipmentWeight": "7.46",
    "pricingDetails": {
        "material": "439.15",
        "discount": 0,
        "misc": 0,
        "handlingCharge": 0,
        "freightCharge": 0.75,
        "tax": 6.2
    },
    "orderTotal": 446.1,
    "itemDetails": [
        {
            "item": "000.30158.2",
            "ordered": 3,
            "shipped": 3,
            "backordered": 0,
            "lotNumber": [],
            "price": 3.13,
            "discount": 0,
            "extendedPrice": 9.39
        },
        {
            "item": "191.57310.3",
            "ordered": 1,
            "shipped": 1,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "AM240074",
                    "quantity": 1,
                    "expirationDate": 20251231
                }
            ],
            "price": 2.17,
            "discount": 0,
            "extendedPrice": 2.17
        },
        {
            "item": "191.57330.3",
            "ordered": 1,
            "shipped": 1,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "AM231524",
                    "quantity": 1,
                    "expirationDate": 20250731
                }
            ],
            "price": 2.64,
            "discount": 0,
            "extendedPrice": 2.64
        },
        {
            "item": "191.64220.3",
            "ordered": 2,
            "shipped": 2,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "396741",
                    "quantity": 2,
                    "expirationDate": 20260731
                }
            ],
            "price": 4.1666,
            "discount": 0,
            "extendedPrice": 8.33
        },
        {
            "item": "193.11592.3",
            "ordered": 2,
            "shipped": 2,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "1000030197",
                    "quantity": 2,
                    "expirationDate": 20260731
                }
            ],
            "price": 32.99,
            "discount": 0,
            "extendedPrice": 65.98
        },
        {
            "item": "193.49492.3",
            "ordered": 3,
            "shipped": 3,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "23313A",
                    "quantity": 3,
                    "expirationDate": 20251130
                }
            ],
            "price": 18.74,
            "discount": 0,
            "extendedPrice": 56.22
        },
        {
            "item": "193.77716.3",
            "ordered": 2,
            "shipped": 2,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "KC01824",
                    "quantity": 2,
                    "expirationDate": 20270131
                }
            ],
            "price": 12.47,
            "discount": 0,
            "extendedPrice": 24.94
        },
        {
            "item": "366.40300.4",
            "ordered": 2,
            "shipped": 2,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "326941X",
                    "quantity": 2,
                    "expirationDate": 20260731
                }
            ],
            "price": 30.92,
            "discount": 0,
            "extendedPrice": 61.84
        },
        {
            "item": "555.04050.3",
            "ordered": 1,
            "shipped": 1,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "GM6727",
                    "quantity": 1,
                    "expirationDate": 20250731
                }
            ],
            "price": 74.55,
            "discount": 0,
            "extendedPrice": 74.55
        },
        {
            "item": "733.97030.3",
            "ordered": 1,
            "shipped": 1,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "315U099A",
                    "quantity": 1,
                    "expirationDate": 20250930
                }
            ],
            "price": 80.67,
            "discount": 0,
            "extendedPrice": 80.67
        },
        {
            "item": "740.13424.3",
            "ordered": 2,
            "shipped": 2,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "00544488001",
                    "quantity": 2,
                    "expirationDate": 20250630
                }
            ],
            "price": 26.21,
            "discount": 0,
            "extendedPrice": 52.42
        },
        {
            "item": "740.13424.3",
            "ordered": 1,
            "shipped": 1,
            "backordered": 0,
            "lotNumber": [
                {
                    "lotNumber": "00544488001",
                    "quantity": 1,
                    "expirationDate": 20250630
                }
            ],
            "price": 0,
            "discount": 0,
            "extendedPrice": 0
        }
    ],
    "trackingNumbers": [
        "1Z17Y07V0302693992"
    ]
}
```