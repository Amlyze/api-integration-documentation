# Account service

## Integration and details

<!-- Swagger Ui `GET https://[host]:[port]/swagger-ui/` (in progress) -->

**Authorization** `Basic Auth`/`Bearer Token`

`POST https://[host]:[port]/amlyze-ws-rest/account (application/json)`

More information account request [account payload.](./fields.md)

The minimalistic request represents scenario of already onboarded customer (`INDIVIDUAL` or `ORGANIZATION`), to whom a new IBAN account (*Not necessarily*) is being attached. All payload fields & descriptions suitable for request.
```json lines
{
  "communicationNumber": "Test_ComNr000",
  "requester": "Company Name Amlyze",
  "businessEntityExtId": "IND_A1_TEST", // --> must match customer identification from /amlyze-ws-rest/customer "customerExtId"
  "accountExtId": "ACC_001",
  "accountNumber": "LI9208800274335945522",
  "accountStatus": "ACTIVE",
  "currencyCode": "EUR",
  "openingDate": "2023-09-05T08:07:34.605Z",
  "bic": "AmlyzeXX22",
  "isOtherFinInstAccount": true  // --> whether account for customer's upcoming operations exists outside your company
}
```
Possible Responses

All possible errors can be found [<u>here.</u>](possibleErrors.md)

```json lines
200 OK
{
  "resultType": "OK"
}

400 Bad Request
{
  "resultType": "REQUEST_REJECTED",
  "errorCode": "O001",
  "errorDescription": "BusinessEntity with given extId does not exist in amlyze"
}

404 Not Found
{
  "timestamp": "2024-05-26T16:49:50.237+00:00",
  "status": 404,
  "error": "Not Found",
  "path": "/amlyze-ws-rest/account" //--> mistake inside the endpoint
}

500 Internal Server Error
{
  "resultType": "REQUEST_REJECTED",
  "status": 500,
  "error": "Internal Server Error"
}
```
