# Batch operation service

<p>
An operation is the transaction between two or more parties, where one of the parties is always the customer. The other party(ies) are called counterparties. The documentation provides information on the endpoints, responses, and possible errors for API requests for operations. It also includes minimalistic request examples.
</p>

## Integration and details

<!-- Swagger Ui `GET https://[host]:[port]/swagger-ui/` (in progress) -->

**Authorization** `Basic Auth`/`Bearer Token`


`POST https://[host]:[port]/amlyze-ws-rest/validate-batch-operations (application/json)` Validate batch of operations without saving

`POST https://[host]:[port]/amlyze-ws-rest/batch-operations (application/json)` Validate batch of operations with saving


> ⚠️ **Warning**: Operations evaluation and screening not available in this service.

The minimalistic request represents operation with the minimum required fields.

```json lines
{
  "operations":[
    {
      "communicationNumber": "SepaComNumber0",
      "requester": "Company Name Amlyze",
      "riskManagementCategory": "OP_TRANSFER",
      "operationType": "SEPA",
      "operationStatus": "EXECUTED",
      "operationExtId": "SepaExtId0",
      "financialFlowDirection": "OUTGOING",
      "operationDateTime": "2023-09-23T15:09:33+02:00",
      "currency": "EUR",
      "amount": 10000,
      "description": "Invoice 'Nr.01'",
      "listOperationParty": [
        { "partyRole": "DEBTOR", "accountNumber": "LI9208800274335945522", "bic": "AmlyzeXX22", "entityType": "INDIVIDUAL", "firstName" : "Tomas", "lastName" : "Garcia" },
        { "partyRole": "CREDITOR", "accountNumber": "LV11245541148212335", "entityType": "ORGANIZATION", "title": "LTD 'VivaFocus'" }
      ]
    },
    {
      "communicationNumber": "SwiftComNumber0",
      "requester": "Company Name Amlyze",
      "riskManagementCategory": "OP_TRANSFER",
      "operationType": "SWIFT",
      "operationStatus": "EXECUTED",
      "operationExtId": "SwiftExtId0",
      "financialFlowDirection": "OUTGOING",
      "operationDateTime": "2023-09-23T15:09:33+02:00",
      "currency": "EUR",
      "amount": 100,
      "description": "Invoice 'Nr.02'",
      "listOperationParty": [
        { "partyRole": "DEBTOR", "accountNumber": "LI9208800274335945522", "bic": "AmlyzeXX22", "entityType": "INDIVIDUAL", "firstName" : "Tomas", "lastName" : "Garcia" },
        { "partyRole": "CREDITOR", "accountNumber": "LV11245541148212335", "entityType": "ORGANIZATION", "title": "LTD 'VivaFocus'" }
      ]
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
      "communicationNumber": "SepaComNumber0",
      "operationExtId": "SepaExtId0",
      "businessUnit": "businessUnit0",
      "timeElapsedMs": 203
    },
    {
      "resultType": "REQUEST_ACCEPTED",
      "communicationNumber": "SwiftComNumber0",
      "operationExtId": "SwiftExtId0",
      "businessUnit": "businessUnit1",
      "timeElapsedMs": 203
    },
  ],
  "timeElapsedMs": 408
}

200 OK
{
  "results": [
    {
      "resultType": "REQUEST_ACCEPTED",
      "communicationNumber": "SepaComNumber0",
      "operationExtId": "SepaExtId0",
      "businessUnit": "businessUnit0",
      "timeElapsedMs": 203
    },
    {
      "resultType": "REQUEST_REJECTED",
      "communicationNumber": "SwiftComNumber0",
      "operationExtId": "SwiftExtId0",
      "businessUnit": "businessUnit1",
      "errorCode": "O005",
      "errorDescription": "Operation with given OperationExtId already exists in Amlyze",
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
  "path": "/amlyze-ws-rest/batch-operations"
}

500 Internal Server Error
{
  "errorCode": "500",
  "errorDescription": "Processing failed",
  "timeElapsedMs": 172
}
```

------

## Available operation types

[<b>SEPA operation</b>](SEPA/fields.md)

---
[<b>SWIFT operation</b>](SWIFT/fields.md)

---

[<b>PIS operation</b>](PIS/fields.md)

---

[<b>INTERNAL operation</b>](INTERNAL/fields.md)

---

[<b>CARD_PAYMENT operation</b>](CARD_PAYMENT/fields.md)

---

[<b>CARD_CASH operation</b>](CARD_CASH/fields.md)

---

[<b>CASH incoming operation</b>](CASH/incoming/fields.md)

[<b>CASH outgoing operation</b>](CASH/outgoing/fields.md)

---
[<b>CASH_TRANSFER operation</b>](CASH_TRANSFER/outgoing/fields.md)

---

[<b>FASTER_PAYMENTS operation</b>](FASTER_PAYMENTS/fields.md)

---

[<b>CRYPTO operation</b>](CRYPTO/fields.md)

---

[<b>CRYPTO_EXCHANGE operation</b>](CRYPTO_EXCHANGE/fields.md)

---
