# Operations

An operation is the transaction between two or more parties, where one of the parties is always the customer. The other party(ies) are called counterparties. The documentation provides information on the endpoints, responses, and possible errors for API requests for operations. It also includes minimalistic request examples.

---

**EndPoint**

<!-- *swagger UI*  `GET / swagger-ui/` -->

`HTTP Method:  POST`

*{{client_test_environment}}*`/amlyze-ws-rest/operation 

 **Headers**

`ContentType: (application/json)`

**Authorization**

`Basic Auth`
`Bearer Token`


## Minimalistic request | SEPA

The Minimalistic request represents SEPA operation with the minimum required fields.
```json
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


## Operation Business Cases | Payload Samples

> Operation Type - **SEPA**

* [Evaluate_SEPA_Full_Ultimates](SEPA/SEPA_Samples/Full_Ultimates.json)
* [Evaluate_SEPA_Mandatory_Ultimates](SEPA/SEPA_Samples/Mandatory_Ultimates.json)
* [Evaluate_SEPA_Full.json](SEPA/SEPA_Samples/evaluate_SEPA_Full.json)
* [Evaluate_SEPA_Mandatory.json](SEPA/SEPA_Samples/evaluate_SEPA_Mandatory.json)
* [Import_SEPA_Full.json](SEPA/SEPA_Samples/import_SEPA_Full.json)
* [Import_SEPA_Mandatory.json](SEPA/SEPA_Samples/import_SEPA_Mandatory.json)

>All payload fields & descriptions suitable for SEPA operation request - [<b>here</b>](SEPA/SEPA_Fields.md)
---

> Operation Type - **SWIFT**
* [Evaluate_SWIFT_Full_Ultimates.json](SWIFT/SWIFT_Samples/Full_Ultimates.json)
* [Evaluate_SWIFT_Mandatory_Ultimates.json](SWIFT/SWIFT_Samples/Mandatory_Ultimates.json)
* [Evaluate_SWIFT_Full.json](SWIFT/SWIFT_Samples/evaluate_SWIFT_Full.json)
* [Evaluate_SWIFT_Mandatory.json](SWIFT/SWIFT_Samples/evaluate_SWIFT_Mandatory.json)
* [Import_SWIFT_Full.json](SWIFT/SWIFT_Samples/import_SWIFT_Full.json)
* [Import_SWIFT_Mandatory.json](SWIFT/SWIFT_Samples/import_SWIFT_Mandatory.json)

>All payload fields & descriptions suitable for SWIFT operation request - [<b>here</b>](SWIFT/SWIFT_Fields.md)
---
> Operation Type - **PIS**
> 
[<b>PIS Fields</b>](PIS/PIS_Fields.md)
* [FullPayload_Evaluate_Screening.json](PIS/PIS_Samples/FullPayload_Evaluate_Screening.json)
* [FullPayload_Import_Screening.json](PIS/PIS_Samples/FullPayload_Import_Screening.json)
* [FullPayload_Ultimates_Evaluate_Screening.json](PIS/PIS_Samples/FullPayload_Ultimates_Evaluate_Screening.json)
* [MinimalisticPayload_Evaluate.json](PIS/PIS_Samples/MinimalisticPayload_Evaluate.json)
* [MinimalisticPayload_Import.json](PIS/PIS_Samples/MinimalisticPayload_Import.json)
* [MinimalisticPayload_Ultimates_Evaluate.json](PIS/PIS_Samples/MinimalisticPayload_Ultimates_Evaluate.json)
---
> Operation Type - **INTERNAL**

[<b>INTERNAL Fields</b>](INTERNAL/fields.md)
* [EvaluateFullUltimates.json](INTERNAL/samples/FullUltimates.json)
* [EvaluateMandatoryUltimates.json](INTERNAL/samples/MandatoryUltimates.json)
* [EvaluateMandatorySameCustomer.json](INTERNAL/samples/EvaluateMandatorySameCustomer.json)
* [EvaluateMandatory.json](INTERNAL/samples/evaluateMandatory.json)
* [ImportFull.json](INTERNAL/samples/importFull.json)
---

> Operation Type - **CARD_PAYMENT**

[<b>CARD_PAYMENT Fields</b>](CARD_PAYMENT/fields.md)
* [EvaluateFull.json](CARD_PAYMENT/samples/evaluateFull.json)
* [EvaluateMandatory.json](CARD_PAYMENT/samples/evaluateMandatory.json)
* [ImportFull.json](CARD_PAYMENT/samples/importFull.json)
* [ImportMandatory.json](CARD_PAYMENT/samples/importMandatory.json)
---
> Operation Type - **CARD_CASH**

[<b>CARD_CASH Fields</b>](CARD_CASH/fields.md)
* [EvaluateFull.json](CARD_CASH/samples/evaluateFull.json)
* [ImportFull.json](CARD_CASH/samples/importFull.json)
* [ImportMandatory.json](CARD_CASH/samples/importMandatory.json)
---
> Operation Type - **CASH**

[<b>CASH Incoming Fields</b>](CASH/incoming/fields.md)
* [evaluateMandatory.json](CASH/incoming/samples/evaluateMandatory.json)
* [evaluateFull.json](CASH/incoming/samples/evaluateFull.json)
* [importMandatory.json](CASH/incoming/samples/importMandatory.json)
* [importFull.json](CASH/incoming/samples/importFull.json)


[<b>CASH Outgoing Fields</b>](CASH/outgoing/fields.md)
* [evaluateMandatory.json](CASH/outgoing/samples/evaluateMandatory.json)
* [evaluateFull.json](CASH/outgoing/samples/evaluateFull.json)
* [importMandatory.json](CASH/outgoing/samples/importMandatory.json)
* [importFull.json](CASH/outgoing/samples/importFull.json)

---
> Operation Type - **CASH_TRANSFER**

[<b>CASH_TRANSFER Outgoing Fields</b>](CASH_TRANSFER/outgoing/fields.md)
* [evaluateFullUltimates.json](CASH_TRANSFER/outgoing/samples/FullUltimates.json)
* [evaluateMandatoryUltimates.json](CASH_TRANSFER/outgoing/samples/MandatoryUltimates.json)
* [evaluateMandatory.json](CASH_TRANSFER/outgoing/samples/evaluateMandatory.json)
* [evaluateFull.json](CASH_TRANSFER/outgoing/samples/evaluateFull.json)
* [importMandatory.json](CASH_TRANSFER/outgoing/samples/importMandatory.json)
* [importFull.json](CASH_TRANSFER/outgoing/samples/importFull.json)

---
> Operation Type - **FASTER_PAYMENTS**

[<b>FASTER_PAYMENTS Fields</b>](FASTER_PAYMENTS/fields.md)
* [EvaluateFull.json](FASTER_PAYMENTS/samples/evaluateFull.json)
* [EvaluateMandatory.json](FASTER_PAYMENTS/samples/evaluateMandatory.json)
* [ImportFull.json](FASTER_PAYMENTS/samples/importFull.json)
* [ImportMandatory.json](FASTER_PAYMENTS/samples/importMandatory.json)
---

> Operation Type - **CRYPTO**

[<b>CRYPTO Fields</b>](CRYPTO/fields.md)
* [EvaluateFull.json](CRYPTO/samples/evaluateFull.json)
* [EvaluateMandatory.json](CRYPTO/samples/evaluateMandatory.json)
* [ImportFull.json](CRYPTO/samples/importFull.json)
* [ImportMandatory.json](CRYPTO/samples/importMandatory.json)
---
> Operation Type - **CRYPTO_EXCHANGE**

[<b>CRYPTO_EXCHANGE Fields</b>](CRYPTO_EXCHANGE/fields.md)
* [EvaluateFull.json](CRYPTO_EXCHANGE/samples/evaluateFull.json)
* [EvaluateMandatory.json](CRYPTO_EXCHANGE/samples/evaluateMandatory.json)
* [ImportFull.json](CRYPTO_EXCHANGE/samples/importFull.json)
* [ImportMandatory.json](CRYPTO_EXCHANGE/samples/importMandatory.json)
---


## Possible Responses

```json
200 OK
  "resultType": "REQUEST_ACCEPTED"


400 Bad Request
    "resultType": "REQUEST_REJECTED",
    "errorCode": "O005",
    "errorDescription": "Operation with given OperationExtId already exists in Amlyze"


404 Not Found
    "timestamp": "2024-05-26T16:49:50.237+00:00",
    "status": 404,
    "error": "Not Found",
    "path": "/amlyze-ws-rest/operationn" --> mistake inside the endpoint


500 Internal Server Error
    "resultType": "REQUEST_REJECTED",
    "errorCode": "500",
    "errorDescription": "failed Processing operation"
```


**Possible Errors | Error Codes**

All possible errors can be found [<u>here</u>](op_possible_errors.md)  


------

