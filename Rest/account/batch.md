# Batch account service

## Integration and details

<!-- Swagger Ui `GET https://[host]:[port]/swagger-ui/` (in progress) -->

**Authorization** `Basic Auth`/`Bearer Token`


`POST https://[host]:[port]/amlyze-ws-rest/validate-batch-accounts (application/json)` Validate batch of accounts without saving

`POST https://[host]:[port]/amlyze-ws-rest/batch-accounts (application/json)` Validate batch of accounts with saving

More information account request [account payload.](./fields.md)

The minimalistic request represents scenario of already onboarded customer (`INDIVIDUAL` or `ORGANIZATION`), to whom a new IBAN account (*Not necessarily*) is being attached. All payload fields & descriptions suitable for request.

```json lines
{
  "accounts":[
    {
      "communicationNumber": "comNumber0",
      "requester": "Company Name Amlyze",
      "businessEntityExtId": "businessEntityExtId0", // --> must match customer identification from /amlyze-ws-rest/customer "customerExtId"
      "accountExtId": "accountExtId0",
      "accountNumber": "LI9208800274335945522",
      "accountStatus": "ACTIVE",
      "currencyCode": "EUR",
      "openingDate": "2023-09-05T08:07:34.605Z",
      "bic": "AmlyzeXX22",
      "isOtherFinInstAccount": true  // --> whether account for customer's upcoming operations exists outside your company
    },
    {
      "communicationNumber": "comNumber1",
      "requester": "Company Name Amlyze",
      "businessEntityExtId": "businessEntityExtId1", // --> must match customer identification from /amlyze-ws-rest/customer "customerExtId"
      "accountExtId": "accountExtId1",
      "accountNumber": "LI9208800274335945523",
      "accountStatus": "ACTIVE",
      "currencyCode": "EUR",
      "openingDate": "2023-09-05T08:07:34.605Z",
      "bic": "AmlyzeXX22"
    }
  ]
}
```

Possible Responses

All possible errors can be found [<u>here.</u>](possibleErrors.md)

```json lines
200 OK
{
  "results": [
    {
      "resultType": "REQUEST_ACCEPTED",
      "communicationNumber": "comNumber0",
      "accountExtId": "accountExtId0",
      "businessUnit": "businessUnit0",
      "timeElapsedMs": 203
    },
    {
      "resultType": "REQUEST_ACCEPTED",
      "communicationNumber": "comNumber1",
      "accountExtId": "accountExtId0",
      "businessUnit": "businessUnit1",
      "timeElapsedMs": 203
    },
  ],
  "timeElapsedMs": 408
}

200 OK
{
  "resultType": "REQUEST_ACCEPTED",
  "results": [
    {
      "resultType": "REQUEST_ACCEPTED",
      "communicationNumber": "comNumber0",
      "accountExtId": "accountExtId0",
      "businessUnit": "businessUnit0",
      "timeElapsedMs": 203
    },
    {
      "resultType": "REQUEST_REJECTED",
      "communicationNumber": "comNumber1",
      "accountExtId": "accountExtId1",
      "businessUnit": "businessUnit1",
      "errorCode": "O005",
      "errorDescription": "CommunicationNumber already used in amlyze",
      "timeElapsedMs": 20
    },
  ],
  "timeElapsedMs": 223
}

400 Bad Request (Invalid json body)
{
  "timestamp": "2024-05-26T16:49:50.237+00:00",
  "status": 400,
  "error": "Bad Request",
  "path": "/amlyze-ws-rest/batch-accounts"
}

500 Internal Server Error
{
  "errorCode": "500",
  "errorDescription": "Processing failed",
  "timeElapsedMs": 172
}
```
