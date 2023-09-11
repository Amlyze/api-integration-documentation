# Operations

An operation is a transaction between two or more parties, where one of the parties is always the customer. The other party(ies) are called counterparties. The documentation provides information on the endpoints, responses, and possible errors for API requests for operations. It also includes minimalistic request examples.

---

## EndPoints

*swagger*  `GET / swagger-ui/`

`POST /amlyze-ws-rest/operation (application/json)`
**URL** : `/amlyze-ws-rest/operation`

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md)

## Samples

* [import_sepa_incoming.json](samples%2Foperation%2Fimport_sepa_incoming.json)
* [import_sepa_outgoing.json](samples%2Foperation%2Fimport_sepa_outgoing.json)


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
  "resultType": "REQUEST_ACCEPTED"
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
    "resultType": "REQUEST_REJECTED",
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
    "screeningLists": [
        "SANCTIONS",
        "PEP",
        "ADVERSE_MEDIA"
    ],
    "sourceOfRiskLevel": "IMPORT",
    "operationStatus":"EXECUTED",
    "operationDateTime": "2023-09-23T15:09:33+02:00",
    "sourceCountry": "LT",
    "destinationCountry": "LV",
    "currency": "EUR",
    "amount": 123,
    "financialFlowDirection": "INCOMING",
    "description": "invoice '123456'",
    "listOperationParty": [
         {
            "partyRole": "DEBTOR",
            "accountNumber": "12345678901234567890",
            "currency": "EUR",
            "bic": "ABCDE",
            "bankTitle": "blah",
            "entityType": "UNKNOWN",
            "title": "asdfg"
        },
        {
            "partyRole": "CREDITOR",
            "accountNumber": "testingOperations_001",
            "currency": "EUR",
            "bic": "TEST",
            "bankTitle": "blah",
            "entityType": "INDIVIDUAL",
            "firstName": "Testas",
            "lastName": "Testauskas"
        }
       
    ]
}
```
