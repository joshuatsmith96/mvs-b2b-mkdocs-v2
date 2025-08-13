# View Code List

### Type of Request: `GET`

### Description
Get a list of all GL Codes.

### Endpoint

Develop: `http://develop:6569/run/ecommerce/wsapi/viewglCodeList?[params]`
Production: `http://mvet:6569/run/ecommerce/wsapi/viewglCodeList?[params]`

Example: `http://develop:6569/run/ecommerce/wsapi/viewglCodeList?customerId=0000850&limit=5&orderBy=description&manufacturer=Zoe`

### Available Parameters (Example)

| Parameter     | Required | Example        |
|---------------|----------|----------------|
|customerId     |True      |0000850         |
|page           |False     |6               |
|limit          |False     |5               |
|orderBy        |False     |description     |
|hasCodeAssigned|False     |true            |
|manufacturer   |False     |Zoetis          |
|item           |False     |123.45678.9     |
|description    |False     |Description     |

### Expected Response
```
{
    "items": [
        {
            "item": "555.00014.3",
            "glcode": "6600",
            "description": "ALFAXAN MD IDX SOL 10mL C-IV  ALFAXOLONE  10mg/ml           10026698",
            "manufacturer": "Zoetis"
        },
        {
            "item": "555.00012.3",
            "glcode": "6600",
            "description": "ALFAXAN MD SOL 20mL C-IV      ALFAXOLONE  10mg/ml           10026697",
            "manufacturer": "Zoetis"
        },
        {
            "item": "553.00001.3",
            "glcode": "6110",
            "description": "CERENIA INJ 10mg/ml 20ml      MAROPITANT CITRATE            10021317",
            "manufacturer": "Zoetis"
        },
        {
            "item": "553.00011.3",
            "glcode": "6105",
            "description": "CERENIA TAB 16mg 40ct         MAROPITANT CITRATE            10025455",
            "manufacturer": "Zoetis"
        },
        {
            "item": "885.10386.3",
            "glcode": "6110",
            "description": "CONVENIA STERILE WATER 10ml                                 10025200",
            "manufacturer": "Zoetis"
        }
    ],
    "total": 32,
    "pages": 7
}
```