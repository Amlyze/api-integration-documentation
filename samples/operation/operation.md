# Operations

adds account to customer profile, used to find customer in operation party

**URL** : `/amlyze-ws-rest/operation`

**METHOD**  `POST`

**Auth required** : NO

**Permissions required** : None

**Data constraints** : 

* at least one operation party account must exist in Amlyze (identified by accountNumber, BIC, Currency)
* communicationNumber must be unique

```json
{
    "communicationNumber": "testing_00000125",
    "requester": "testing",
    "operationExtId": "testing_00000123",
    "operationType": "SEPA",
    "riskManagementCategory": "OP_INST",
    "screeningLists": [
        "SANCTIONS"
    ],
    "sourceOfRiskLevel": "IMPORT",
    "operationStatus":"EXECUTED",
    "operationDateTime": "{{$isoTimestamp}}",
    "destinationCountry": "LT",
    "currency": "EUR",
    "amount": 123,
    "financialFlowDirection": "INCOMING",
    "description": "invoice '123456'",
    "listOperationParty": [
        {
            "partyRole": "CREDITOR",
            "accountNumber": "testingOperations_001",
            "currency": "EUR",
            "bic": "TEST",
            "bankTitle": "blah",
            "entityType": "INDIVIDUAL",
            "firstName": "Testas",
            "lastName": "Testauskas"
        },
        {
            "partyRole": "DEBTOR",
            "accountNumber": "12345678901234567890",
            "currency": "EUR",
            "bic": "ABCDE",
            "bankTitle": "blah",
            "entityType": "UNKNOWN",
            "title": "asdfg"
        }
    ]
}
```


**possible fields**
[fields.md](fields.md)

## Samples

* [import_sepa_incoming.json](samples%2Foperation%2Fimport_sepa_incoming.json)
* [import_sepa_outgoing.json](samples%2Foperation%2Fimport_sepa_outgoing.json)

## Success Response

**Condition** : If everything is OK.

**Code** : `202 Request Accepted`

**Content example**

```json
{
  "resultType": "REQUEST_ACCEPTED"
}
```

## Business ERROR Response

**Condition** : If there are some inconsistencies with data

**Code** : `500 Internal Server Error`

**Content example**
```json
{
  "resultType": "REQUEST_REJECTED",
  "errorDescription": "duplicate communicationNumber"
}
```

### Possible errors

* `CommunicationNumber is mandatory`
* `RiskManagementCategory is mandatory`
* `RiskManagementCategory does not exist in amlyze`
* `Requester is mandatory` 
* `SourceOfRiskLevel is mandatory, allowed values: IMPORT / EVALUATE.`
* `OperationExtId is mandatory`
* `OperationType is mandatory`
* `Problem with OperationType (INVALID).  INVALID is not defined in Amlyze. Check Operation type classifier for available values.`
* `OperationDateTime is mandatory.`
* `Currency is mandatory, check Currency classifier codes for alowed values.`
* `Currency is mandatory, check Currency classifier codes for alowed values.`
* `SourceCountry is mandatory, check country classifier codes for alowed values.`
* `DestinationCountry is mandatory, check country classifier codes for alowed values.`
* `Description is mandatory`
* `Problem with OperationType (SEPA).  Problem with OperationParties.  No operation party account related to your institution BIC, or Customer`
* `Invalid FinancialFlowDirection. Your institution CREDITOR found for OUTGOING operation`
* `Problem with OperationType (SEPA).  Problem with OperationParties.  Invalid count of your institution operation parties for SEPA operationType`
