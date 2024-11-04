# Batch account balances registration (coming soon❗)

This section provides detailed information on the endpoints that can be used to create and manage account balances.


----

## EndPoints

<!-- *swagger UI*  `GET / swagger-ui/` -->

`PUT /amlyze-ws-rest/batch-account-balances (application/json)`

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](./fields.md)

---

## Minimalistic request

The minimalistic request example below shows the minimum required fields to successfully add an account.

```json lines
{
  "accountBalances": [
    {
      "communicationNumber": "commNumber0",
      "requester": "financial_institution",
      "balanceType": "DAILY_BALANCE",
      "accountExtId": "accountExtId0",
      "businessUnit": "businessUnit0",
      "updateAt": "2023-09-05T08:07:34.605Z",
      "value": 11111111111.00,
      "equivalentValue": 33333.00
    },
    {
      "communicationNumber": "commNumber1",
      "requester": "financial_institution",
      "balanceType": "DAILY_BALANCE",
      "accountExtId": "accountExtId1",
      "businessUnit": "businessUnit1",
      "updateAt": "2023-09-05T08:07:34.605Z",
      "value": 11111111111.00
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
      "communicationNumber": "commNumber0",
      "accountExtId": "accountExtId0",
      "businessUnit": "businessUnit0",
      "timeElapsedMs": 203
    },
    {
      "resultType": "REQUEST_REJECTED",
      "communicationNumber": "CommNumber1",
      "accountExtId": "accountExtId1",
      "businessUnit": "businessUnit1",
      "errorCode": "O005",
      "errorDescription": "CommunicationNumber already used in amlyze",
      "timeElapsedMs": 20
    },
  ],
  "timeElapsedMs": 223
}

404 Not Found
{
  "timestamp": "2024-05-26T16:49:50.237+00:00",
  "status": 404,
  "error": "Not Found",
  "path": "/amlyze-ws-rest/batch-account-balances" //--> mistake inside the endpoint
}

500 Internal Server Error
{
  "resultType": "REQUEST_REJECTED",
  "status": 500,
  "error": "Internal Server Error"
}
```

