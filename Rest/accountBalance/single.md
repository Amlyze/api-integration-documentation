# Account balance registration

This section provides detailed information on the endpoints that can be used to create and manage account balances..


----

## EndPoints

<!-- *swagger UI*  `GET / swagger-ui/` -->

`PUT /amlyze-ws-rest/account-balance (application/json)` (Update account balance)

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md)

---

## Minimalistic request

The minimalistic request example below shows the minimum required fields to successfully add an account.

```json lines
{
  "communicationNumber": "COM216a",
  "requester": "financial_institution",
  "balanceType": "DAILY_BALANCE",
  "accountExtId": "any_account_ext_id_1232",
  "businessUnit": "BU_1",
  "balanceAt": "2023-09-05T08:07:34.605Z",
  "value": 11111111111.00,
  "equivalentValue": 33333.00
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
  "errorDescription": "extId is mandatory"
}

404 Not Found
{
  "timestamp": "2024-05-26T16:49:50.237+00:00",
  "status": 404,
  "error": "Not Found",
  "path": "/amlyze-ws-rest/account-balance" //--> mistake inside the endpoint
}

500 Internal Server Error
{
  "resultType": "REQUEST_REJECTED",
  "status": 500,
  "error": "Internal Server Error"
}
```

----


