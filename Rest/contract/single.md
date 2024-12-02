# Contract registration

This section provides detailed information on the endpoints that can be used to create and manage contracts. Contracts can be any type of documents with custom set of fields/elements.


----

## EndPoints

<!-- *swagger UI*  `GET / swagger-ui/` -->

`POST /amlyze-ws-rest/contract (application/json)` (Create contract)

`PUT /amlyze-ws-rest/contract (application/json)` (Update contract)

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md)

---

## Minimalistic request

The minimalistic request example below shows the minimum required fields to successfully add an account.

```json lines
{
    "communicationNumber": "COM216a",
    "requester": "financial_institution",
    "contractType": "LOAN",
    "extId": "any_contract_1232",
    "contractCode": "REG74121101"
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
  "path": "/amlyze-ws-rest/contract" //--> mistake inside the endpoint
}

500 Internal Server Error
{
  "resultType": "REQUEST_REJECTED",
  "status": 500,
  "error": "Internal Server Error"
}
```

----


