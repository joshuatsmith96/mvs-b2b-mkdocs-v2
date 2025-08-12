# Account Statements

### Type of Request: `GET`

### Description
This API retrieves account statements for an account.

### Endpoint

- Develop: `http://develop:6569/run/ecommerce/wsapi/accountstatements?[params]`
- Production: `http://mvet:6569/run/ecommerce/wsapi/accountstatements?[params]`
- Example: `http://develop:6569/run/ecommerce/wsapi/accountstatements?statementDate=2024-06&customerId=0013265`

### Available Parameters

| Parameter     | Required | Example        |
|---------------|----------|----------------|
| customerID    | True     | 0013265        |
| statementDate | False    | 2024-06        |

### Expected Response

Response should be a PDF