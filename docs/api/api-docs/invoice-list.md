# Invoice List

### Type of Request: `GET`

### Description
API used to retrieve a list of invoices based on a customerId and various other optional parameters.

### Endpoint

Develop: `http://develop:6565/run/ecommerce/wsapi/invoice/list?[params]`

Production: `http://develop:6565/run/ecommerce/wsapi/invoice/list?[params]`

Example: `http://develop:6565/run/ecommerce/wsapi/invoice/list?page=1&customer=0004027&shipTo=0004029&item=042.10119.2&limit=10`

### Available Parameters

| Parameter | Required | Example     |
| --------- | -------- | ----------- |
| customer  | true    | 0004027     |
| shipTo    | false    | 0004029     |
| fromDate  | false    | 20240616    |
| toDate    | false    | 20250716    |
| itemDescription | false    | Description |
| poNumber  | false    | PONumber123            |
| page      | false    | 1           |
| item      | false    | 042.10119.2 |
| limit     | false    | 10          |


### Expected Response

```
{
    "pagination": {
        "totalRecords": 1,
        "currentRecordRange": "1-10",
        "totalPages": 1,
        "currentPage": 1
    },
    "invoices": [
        {
            "accountNumber": "0004027-0004029",
            "accountName": "B W FURLONG & ASSOCIATES",
            "orderNumber": 23142506,
            "invoiceNumber": "23142506-000",
            "status": "INVOICED",
            "customerPO": "",
            "orderDate": 20240906,
            "shippedDate": 20240917,
            "orderTotal": 14763.33
        }
    ]
}
```