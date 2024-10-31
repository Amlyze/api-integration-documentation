# Customer service

## Integration and details

<!-- Swagger Ui `GET https://[host]:[port]/swagger-ui/` (in progress) -->

**Authorization** `Basic Auth`/`Bearer Token`

`POST https://[host]:[port]/amlyze-ws-rest/customer (application/json)`

The minimalistic request represents customer with the minimum required fields.
```json lines
{
  "communicationNumber" : "Test_ComNr000",
  "requester" : "Company Name Amlyze",
  "action" : "CREATE",
  "sourceOfRiskLevel" : "EVALUATE",
  "riskManagementCategory": "IND",
  "customerExtId" : "IND_A1_TEST",
  "entityType" : "INDIVIDUAL",
  "applicationDate": "2023-10-01",
  "firstName" : "Tomas",
  "lastName" : "Garcia",
  "citizenshipCountry" : "LT"
}
```
Possible Responses

All possible errors can be found [<u>here.</u>](possibleErrors.md)

```json lines
200 OK
{
  "resultType": "REQUEST_ACCEPTED"
}

400 Bad Request
{
  "resultType": "REQUEST_REJECTED",
  "errorCode": "O001",
  "errorDescription": "CommunicationNumber already used in amlyze"
}

404 Not Found
{
  "timestamp": "2024-05-26T16:49:50.237+00:00",
  "status": 404,
  "error": "Not Found",
  "path": "/amlyze-ws-rest/customerr" //--> mistake inside the endpoint
}

500 Internal Server Error
{
  "resultType": "REQUEST_REJECTED",
  "status": 500,
  "error": "Internal Server Error"
}
```

------

## Available customer types

[<b>Individual</b>](./individual/fields.md)

---
[<b>Organization</b>](./organization/fields.md)

---
