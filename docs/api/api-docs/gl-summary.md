# GL Code Summaries

### Type of Request: `GET`

### Description
Retrieve a summary for a GL Code.

### Endpoint

Develop: `http://develop:6569/run/ecommerce/wsapi/glcodesummary?[params]`

Production: `http://mvet:6569/run/ecommerce/wsapi/glcodesummary?[params]`

Example: `http://develop:6569/run/ecommerce/wsapi/glcodesummary?customerId=0004027&limit=&startDate=2025-01-01&endDate=2025-01-31`

### Available Parameters

| Parameter     | Required | Example        |
|---------------|----------|----------------|
|customerId     |True      |0004027         |
|limit          |False     |5               |
|page           |False     |1               |
|startDate      |False     |2025-01-01      |
|endDate        |False     |2025-01-31      |

### Expected Response
```
{
    "records": [
        {
            "glcode": "*None",
            "invoiced": -3649.88,
            "tax": 0,
            "misc": 0,
            "shipping": 0,
            "total": -3649.88
        },
        {
            "glcode": "6020",
            "invoiced": 2584.87,
            "tax": 153.45,
            "misc": 0,
            "shipping": 0,
            "total": 2738.32
        },
        {
            "glcode": "6025",
            "invoiced": 1626.19,
            "tax": 105.83,
            "misc": 0,
            "shipping": 0,
            "total": 1732.02
        },
        {
            "glcode": "6105",
            "invoiced": 2708.56,
            "tax": 35.33,
            "misc": 0,
            "shipping": 0,
            "total": 2743.89
        },
        {
            "glcode": "6110",
            "invoiced": 1557.85,
            "tax": 18.02,
            "misc": 0,
            "shipping": 0,
            "total": 1575.87
        },
        {
            "glcode": "Shipping",
            "invoiced": 0,
            "tax": 0,
            "misc": 0,
            "shipping": 18.75,
            "total": 18.75
        }
    ],
    "grandTotals": {
        "invoiced": "7756.92",
        "tax": "368.32",
        "misc": "0.00",
        "shipping": "18.75",
        "total": "8143.99"
    },
    "shippingTotal": "18.75",
    "returnTotal": "227.28",
    "totalCount": 9,
    "pages": 2
}
```