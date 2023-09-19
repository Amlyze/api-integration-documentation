# Operations

An operation is a transaction between two or more parties, where one of the parties is always the customer. The other party(ies) are called counterparties. The documentation provides information on the endpoints, responses, and possible errors for API requests for operations. It also includes minimalistic request examples.

---

## EndPoints

*swagger UI*  `GET / swagger-ui/`

`POST /amlyze-ws-rest/operation (application/json)`


The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md)

## Samples

* [Evaluate_SEPA_Full.json](samples/evaluate_SEPA_Full.json)
* [Evaluate_SEPA_Mandatory.json](samples/evaluate_SEPA_Mandatory.json)
* [Import_SEPA_Full.json](samples/import_SEPA_Full.json)
* [Import_SEPA_Mandatory.json](samples/import_SEPA_Mandatory.json)
---
* [Evaluate_SWIFT_Full.json](samples/evaluate_SWIFT_Full.json)
* [Evaluate_SWIFT_Mandatory.json](samples/evaluate_SWIFT_Mandatory.json)
* [Import_SWIFT_Full.json](samples/import_SWIFT_Full.json)
* [Import_SWIFT_Mandatory.json](samples/import_SWIFT_Mandatory.json)
---
* [Evaluate_PIS_Full.json](samples/evaluate_PIS_Full.json)
* [Evaluate_PIS_Mandatory.json](samples/evaluate_PIS_Mandatory.json)
* [Import_PIS_Full.json](samples/import_PIS_Full.json)
* [Import_PIS_Mandatory.json](samples/import_PIS_Mandatory.json)
---
* [Evaluate_INTERNAL_Full.json](samples/evaluate_INTERNAL_Full.json)
* [Evaluate_INTERNAL_Mandatory.json](samples/evaluate_INTERNAL_Mandatory.json)
* [Import_INTERNAL_Full.json](samples/import_INTERNAL_Full.json)
* [Import_INTERNAL_Mandatory.json](samples/import_INTERNAL_Mandatory.json)
---
* [Evaluate_CARD_PAYMENT_Full.json](samples/evaluate_CARD_PAYMENT_Full.json)
* [Evaluate_CARD_PAYMENT_Mandatory.json](samples/evaluate_CARD_PAYMENT_Mandatory.json)
* [Import_CARD_PAYMENT_Full.json](samples/import_CARD_PAYMENT_Full.json)
* [Import_CARD_PAYMENT_Mandatory.json](samples/import_CARD_PAYMENT_Mandatory.json)
---
* [Evaluate_CARD_CASH_Full.json](samples/evaluate_CARD_PAYMENT_Full.json)
* [Evaluate_CARD_CASH_Mandatory.json](samples/evaluate_CARD_CASH_Mandatory.json)
* [Import_CARD_CASH_Full.json](samples/import_CARD_CASH_Full.json)
* [Import_CARD_CASH_Mandatory.json](samples/import_CARD_CASH_Mandatory.json)
---
* [Evaluate_FASTER_PAYMENTS_Full.json](samples/evaluate_FASTER_PAYMENTS_Full.json)
* [Evaluate_FASTER_PAYMENTS_Mandatory.json](samples/evaluate_FASTER_PAYMENTS_Mandatory.json)
* [Import_FASTER_PAYMENTS_Full.json](samples/import_FASTER_PAYMENTS_Full.json)
* [Import_FASTER_PAYMENTS_Mandatory.json](samples/import_FASTER_PAYMENTS_Mandatory.json)
---
* [Evaluate_CRYPTO_Full.json](samples/evaluate_CRYPTO_Full.json)
* [Evaluate_CRYPTO_Mandatory.json](samples/evaluate_CRYPTO_Mandatory.json)
* [Import_CRYPTO_Full.json](samples/import_CRYPTO_Full.json)
* [Import_CRYPTO_Mandatory.json](samples/import_CRYPTO_Mandatory.json)
---
* [Evaluate_CRYPTO_EXCHANGE_Full.json](samples/evaluate_CRYPTO_EXCHANGE_Full.json)
* [Evaluate_CRYPTO_EXCHANGE_Mandatory.json](samples/evaluate_CRYPTO_EXCHANGE_Mandatory.json)
* [Import_CRYPTO_EXCHANGE_Full.json](samples/import_CRYPTO_EXCHANGE_Full.json)
* [Import_CRYPTO_EXCHANGE_Mandatory.json](samples/import_CRYPTO_EXCHANGE_Mandatory.json)
---


## Responses

<table>
		<thead>
			<tr>
				<td style="text-align:center"><b>Code<b></td>
				<td style="text-align:center"><b>Status<b></td>
				<td style="text-align:center"><b>Response<b></td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><b>200<b></td>
				<td style="text-align:center"><i>OK<i></td>
				<td>
					<pre><b>{
  "resultType": "OK"
}
				</td>
			</tr>
			<tr>
				<td><b>400<b></td>
				<td style="text-align:center"><i>Bad Request<i></td>
				<td> <pre><b>
{
    "errors": [
        "entityType is mandatory"
  ]
}
				</td>
			</tr>
            <tr>
				<td><b>404<b></td>
				<td style="text-align:center"><i>Not Found<i></td>
				<td> <pre><b>
{
    "timestamp": "2023-09-08T05:55:12.219+00:00",
    "status": 404,
    "error": "Not Found",
    "path": "/amlyze-ws-rest/operationn"
}
				</td>
			</tr>
			<tr>
				<td><b>500<b></td>
				<td style="text-align:center"><i>Internal Server Error<i></td>
				<td> <pre><b>{
    "resultType": "ERROR",
    "errorDescription": "duplicate communicationNumber"
}
				</td>
			</tr>
		</tbody>
</table>


**Possible errorrs**

All possible errors can be found [*here*](op_possible_errors.md)  


------

## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully create an operation. Other fields may be optionally included, as specified in the API documentation which that can be found [*here*](fields.md).

```json
{
    "communicationNumber": "ComNr_0012",
    "requester": "Financial_Institution",
    "operationExtId": "Op_0013",
    "operationType": "SEPA",
    "riskManagementCategory": "OP_INST",
    "sourceOfRiskLevel": "IMPORT",
    "operationStatus":"EXECUTED",
    "operationDateTime": "2023-09-23T15:09:33+02:00",
    "currency": "EUR",
    "amount": 125,
    "financialFlowDirection": "OUTGOING",
    "description": "invoice '123456'",
    "listOperationParty": [
         {
            "partyRole": "DEBTOR",
            "accountNumber": "LT5630800200000011112",
            "currency": "EUR",
            "bic": "BIC22XX",
            "entityType": "ORGANIZATION",
            "title": "Komapnele"
        },
        {
            "partyRole": "CREDITOR",
            "accountNumber": "LV11245541148212335",
            "currency": "EUR",
            "entityType": "INDIVIDUAL",
            "firstName": "Testio",
            "lastName": "Testonio"
        }
       
    ]
}
```
