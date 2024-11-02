# Batch contract registration (coming soon❗)

This section provides detailed information on the endpoints that can be used to create and manage contracts. Contracts can be any type of documents with custom set of fields/elements.


----

## EndPoints

<!-- *swagger UI*  `GET / swagger-ui/` -->

`POST /amlyze-ws-rest/validate-batch-contracts (application/json)`
`POST /amlyze-ws-rest/batch-contracts (application/json)`

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](./fields.md)

---

## Minimalistic request

The minimalistic request example below shows the minimum required fields to successfully add an account.

```json lines
{
  "contracts": [
    {
      "action": "CREATE",
      "communicationNumber": "CommNumber0",
      "requester": "financial_institution",
      "classifierType": "LOAN",
      "extId": "any_contract_1",
      "documentCode": "REG74121101"
    },
    {
      "action": "UPDATE",
      "communicationNumber": "CommNumber1",
      "requester": "financial_institution",
      "classifierType": "LOAN",
      "extId": "any_contract_2",
      "documentCode": "REG74121102"
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
      "communicationNumber": "CommNumber0",
      "extId": "any_contract_1",
      "businessUnit": "businessUnit0",
      "timeElapsedMs": 203
    },
    {
      "resultType": "REQUEST_REJECTED",
      "communicationNumber": "CommNumber1",
      "extId": "any_contract_2",
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
  "path": "/amlyze-ws-rest/batch-contracts" //--> mistake inside the endpoint
}

500 Internal Server Error
{
  "resultType": "REQUEST_REJECTED",
  "status": 500,
  "error": "Internal Server Error"
}
```

