# Operations

An operation is a transaction between two or more parties, where one of the parties is always the customer. The other party(ies) are called counterparties. The documentation provides information on the endpoints, responses, and possible errors for API requests for operations. It also includes minimalistic request examples.

---

## EndPoints

*swagger UI*  `GET / swagger-ui/`

`POST /amlyze-ws-rest/operation (application/json)`


## Samples


[<b>SEPA Fields</b>](SEPA/SEPA_Fields.md)
* [Evaluate_SEPA_Full.json](SEPA/SEPA_Samples/evaluate_SEPA_Full.json)
* [Evaluate_SEPA_Mandatory.json](SEPA/SEPA_Samples/evaluate_SEPA_Mandatory.json)
* [Import_SEPA_Full.json](SEPA/SEPA_Samples/import_SEPA_Full.json)
* [Import_SEPA_Mandatory.json](SEPA/SEPA_Samples/import_SEPA_Mandatory.json)
---

[<b>SWIFT Fields</b>](SWIFT/SWIFT_Fields.md)
* [Evaluate_SWIFT_Full.json](SWIFT/SWIFT_Samples/evaluate_SWIFT_Full.json)
* [Evaluate_SWIFT_Mandatory.json](SWIFT/SWIFT_Samples/evaluate_SWIFT_Mandatory.json)
* [Import_SWIFT_Full.json](SWIFT/SWIFT_Samples/import_SWIFT_Full.json)
* [Import_SWIFT_Mandatory.json](SWIFT/SWIFT_Samples/import_SWIFT_Mandatory.json)
---

[<b>PIS Fields</b>](PIS/PIS_Fields.md)
* [Evaluate_PIS_Full.json](PIS/PIS_Samples/evaluate_PIS_Full.json)
* [Evaluate_PIS_Mandatory.json](PIS/PIS_Samples/evaluate_PIS_Mandatory.json)
* [Import_PIS_Full.json](PIS/PIS_Samples/import_PIS_Full.json)
* [Import_PIS_Mandatory.json](PIS/PIS_Samples/import_PIS_Mandatory.json)
---

[<b>INTERNAL Fields</b>](INTERNAL/INTERNAL_Fields.md)
* [Evaluate_INTERNAL_Full.json](INTERNAL/INTERNAL_Samples/evaluate_INTERNAL_Full.json)
* [Evaluate_INTERNAL_Mandatory.json](INTERNAL/INTERNAL_Samples/evaluate_INTERNAL_Mandatory.json)
* [Import_INTERNAL_Full.json](INTERNAL/INTERNAL_Samples/import_INTERNAL_Full.json)
* [Import_INTERNAL_Mandatory.json](INTERNAL/INTERNAL_Samples/import_INTERNAL_Mandatory.json)
---

[<b>CARD_PAYMENT Fields</b>](CARD_PAYMENT/CARD_PAYMENT_Fields.md)
* [Evaluate_CARD_PAYMENT_Full.json](samples/evaluate_CARD_PAYMENT_Full.json)
* [Evaluate_CARD_PAYMENT_Mandatory.json](samples/evaluate_CARD_PAYMENT_Mandatory.json)
* [Import_CARD_PAYMENT_Full.json](samples/import_CARD_PAYMENT_Full.json)
* [Import_CARD_PAYMENT_Mandatory.json](samples/import_CARD_PAYMENT_Mandatory.json)
---

[<b>CARD_CASH Fields</b>](CARD_CASH/CARD_CASH_Fields.md)
* [Evaluate_CARD_CASH_Full.json](CARD_CASH/CARD_CASH_Samples/evaluate_CARD_PAYMENT_Full.json)
* [Evaluate_CARD_CASH_Mandatory.json](CARD_CASH/CARD_CASH_Samples/evaluate_CARD_CASH_Mandatory.json)
* [Import_CARD_CASH_Full.json](CARD_CASH/CARD_CASH_Samples/import_CARD_CASH_Full.json)
* [Import_CARD_CASH_Mandatory.json](CARD_CASH/CARD_CASH_Samples/import_CARD_CASH_Mandatory.json)
---

[<b>FASTER_PAYMENTS Fields</b>](FASTER_PAYMENTS/FASTER_PAYMENTS_Fields.md)
* [Evaluate_FASTER_PAYMENTS_Full.json](FASTER_PAYMENTS/FASTER_PAYMENTS_Samples/evaluate_FASTER_PAYMENTS_Full.json)
* [Evaluate_FASTER_PAYMENTS_Mandatory.json](FASTER_PAYMENTS/FASTER_PAYMENTS_Samples/evaluate_FASTER_PAYMENTS_Mandatory.json)
* [Import_FASTER_PAYMENTS_Full.json](FASTER_PAYMENTS/FASTER_PAYMENTS_Samples/import_FASTER_PAYMENTS_Full.json)
* [Import_FASTER_PAYMENTS_Mandatory.json](FASTER_PAYMENTS/FASTER_PAYMENTS_Samples/import_FASTER_PAYMENTS_Mandatory.json)
---

[<b>CRYPTO Fields</b>](CRYPTO/CRYPTO_Fields.md)
* [Evaluate_CRYPTO_Full.json](CRYPTO/CRYPTO_Samples/evaluate_CRYPTO_Full.json)
* [Evaluate_CRYPTO_Mandatory.json](CRYPTO/CRYPTO_Samples/evaluate_CRYPTO_Mandatory.json)
* [Import_CRYPTO_Full.json](CRYPTO/CRYPTO_Samples/import_CRYPTO_Full.json)
* [Import_CRYPTO_Mandatory.json](CRYPTO/CRYPTO_Samples/import_CRYPTO_Mandatory.json)
---

[<b>CRYPTO_EXCHANGE Fields</b>](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Fields.md)
* [Evaluate_CRYPTO_EXCHANGE_Full.json](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Samples/evaluate_CRYPTO_EXCHANGE_Full.json)
* [Evaluate_CRYPTO_EXCHANGE_Mandatory.json](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Samples/evaluate_CRYPTO_EXCHANGE_Mandatory.json)
* [Import_CRYPTO_EXCHANGE_Full.json](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Samples/import_CRYPTO_EXCHANGE_Full.json)
* [Import_CRYPTO_EXCHANGE_Mandatory.json](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Samples/import_CRYPTO_EXCHANGE_Mandatory.json)
---


## Responses

<table>
		<thead>
			<tr>
				<td style="text-align:center"><b>Code</b></td>
				<td style="text-align:center"><b>Status</b></td>
				<td style="text-align:center"><b>Response</b></td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><b>200</b></td>
				<td style="text-align:center"><i>OK</i></td>
				<td>
					<pre>
{
  "resultType": "OK"
}
                    </pre>
				</td>
			</tr>
			<tr>
				<td><b>400</b></td>
				<td style="text-align:center"><i>Bad Request</i></td>
				<td> <pre>
{
    "errors": [
        "entityType is mandatory"
  ]
}
                    </pre>
				</td>
			</tr>
            <tr>
				<td><b>404</b></td>
				<td style="text-align:center"><i>Not Found</i></td>
				<td>
                    <pre>
{
    "timestamp": "2023-09-08T05:55:12.219+00:00",
    "status": 404,
    "error": "Not Found",
    "path": "/amlyze-ws-rest/operationn"
}
                    </pre>
				</td>
			</tr>
			<tr>
				<td><b>500</b></td>
				<td style="text-align:center"><i>Internal Server Error</i></td>
				<td> 
                    <pre>
{
    "resultType": "ERROR",
    "errorDescription": "duplicate communicationNumber"
}
                    </pre>
				</td>
			</tr>
		</tbody>
</table>


**Possible errorrs**

All possible errors can be found [*here*](op_possible_errors.md)  


------

## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully create an operation. Other fields may be optionally included, as specified in the API documentation.

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
            "bic": "BIC22XX",
            "entityType": "ORGANIZATION",
            "title": "Komapnele"
        },
        {
            "partyRole": "CREDITOR",
            "accountNumber": "LV11245541148212335",
            "entityType": "INDIVIDUAL",
            "firstName": "Testio",
            "lastName": "Testonio"
        }
       
    ]
}
```
