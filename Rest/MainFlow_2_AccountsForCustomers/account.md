# Account 


----

**Endpoint**

<!-- *swagger UI*  `GET / swagger-ui/` -->

`HTTP Method:  POST`

*{{client_test_environment}}*`/amlyze-ws-rest/account`

 **Headers**

`ContentType: (application/json)`

**Authorization**

`Basic Auth`
`Bearer Token`

------


## Body | Minimalistic request


The Minimalistic request represents scenario of already onboarded customer (`INDIVIDUAL` or `ORGANIZATION`), to whom a new IBAN account (*Not necessarily*) is being attached. All payload fields & descriptions suitable for request - [<u>here</u>](fields.md).

```json
{
  "communicationNumber": "Test_ComNr000",
  "requester": "Company Name Amlyze",
  "businessEntityExtId": "IND_A1_TEST", --> must match customer identification from /amlyze-ws-rest/customer "customerExtId"
  "accountExtId": "ACC_001",
  "accountNumber": "LI9208800274335945522",
  "accountStatus": "ACTIVE",
  "currencyCode": "EUR",
  "openingDate": "2023-09-05T08:07:34.605Z",
  "bic": "AmlyzeXX22",
  "isOtherFinInstAccount": true,  --> whether account for customer's upcoming operations exists outside your company 
  
}

```

## Account | Payload Samples

1. [Minimalistic Active Account Payload](../1.1_account/AccountBusinessCases/account_active_minimalistic.json)
2. [Account Belongs To Other Financial Institution](../1.1_account/AccountBusinessCases/account_active_otherFinancialInstitution.json)
3. [Account Is Closed](../1.1_account/AccountBusinessCases/account_closed.json)
4. [Account Is Suspended](../1.1_account/AccountBusinessCases/account_suspended.json)

---

## Possible Responses

```json
200 OK
  "resultType": "OK"


400 Bad Request
    "resultType": "ERROR",
    "errorCode": "404",
    "errorDescription": "BusinessEntity with given extId does not exist in amlyze"


404 Not Found
    "timestamp": "2024-05-27T08:23:44.205+00:00",
    "status": 404,
    "error": "Not Found",
    "path": "/amlyze-ws-rest/accountt" --> mistake inside the endpoint


500 Internal Server Error
  "resultType": "REQUEST_REJECTED"
  "status": 500,
  "error": "Internal Server Error"
```
----
## Possible Errors | Error Codes

All possible errors can be found [<u>here</u>](acc_possible_errors.md)  


----




