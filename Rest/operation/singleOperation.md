# Operation service

<p>
An operation is the transaction between two or more parties, where one of the parties is always the customer. The other party(ies) are called counterparties. The documentation provides information on the endpoints, responses, and possible errors for API requests for operations. It also includes minimalistic request examples.
</p>

## Integration and details

<!-- Swagger Ui `GET https://[host]:[port]/swagger-ui/` (in progress) -->

**Authorization** `Basic Auth`/`Bearer Token`

`POST https://[host]:[port]/amlyze-ws-rest/operation (application/json)`

The minimalistic request represents operation with the minimum required fields.
```json lines
{
    "communicationNumber": "Test_ComNr0010",
    "requester": "Company Name Amlyze",
    "sourceOfRiskLevel": "EVALUATE",
    "riskManagementCategory": "OP_TRANSFER",
    "operationType": "SEPA",
    "operationExtId": "Op_0001_TEST",
    "financialFlowDirection": "OUTGOING",
    "operationDateTime": "2023-09-23T15:09:33+02:00",
    "currency": "EUR",
    "amount": 10000,
    "description": "Invoice 'Nr.01'",
    "listOperationParty": [
         {
            "partyRole": "DEBTOR",
            "accountNumber": "LI9208800274335945522",
            "bic": "AmlyzeXX22",
            "entityType": "INDIVIDUAL",
           	"firstName" : "Tomas",
	        "lastName" : "Garcia"
        },
        {
            "partyRole": "CREDITOR",
            "accountNumber": "LV11245541148212335",
            "entityType": "ORGANIZATION",
            "title": "LTD 'VivaFocus'"
        }
       
    ]
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
  "errorCode": "O005",
  "errorDescription": "Operation with given OperationExtId already exists in Amlyze"
}

404 Not Found
{
  "timestamp": "2024-05-26T16:49:50.237+00:00",
  "status": 404,
  "error": "Not Found",
  "path": "/amlyze-ws-rest/operationn" //--> mistake inside the endpoint
}

500 Internal Server Error
{
  "resultType": "REQUEST_REJECTED",
  "errorCode": "500",
  "errorDescription": "Processing failed"
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