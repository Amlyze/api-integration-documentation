# Customer


------------

**Endpoint**


`HTTP Method:  POST`

*{{client_test_environment}}*`/amlyze-ws-rest/customer `

 **Headers**

`ContentType: (application/json)`

**Authorization**

`Basic Auth`
`Bearer Token`

------


## Body | Minimalistic request

>The Minimalistic request represents minimal data needed to provide in order to initiate customer-**individual** *evaluation*. 



```json
{
	"communicationNumber" : "Test_ComNr000", 
	"requester" : "Company Name Amlyze",
	"action" : "CREATE",

	"sourceOfRiskLevel" : "EVALUATE", 
	"riskManagementCategory": "IND",

	"customerExtId" : "IND_A1_TEST",
	"entityType" : "INDIVIDUAL",

	"applicationDate": "2023-10-01",
	"firstName" : "Tomas",
	"lastName" : "Garcia",
	"citizenshipCountry" : "LT"
}
```
---

## Customer Business Cases | Payload Samples

>Customer - INDIVIDUAL

1. [Entity Data Scan Initiation](../1_customer_business_cases/Customer%20INDIVIDUAL/Business%20Cases%20Samples/EV_A1_Entity%20Data%20Scan%20Initiation.json) 
1.1. [Entity Data Overwrite + Scan Reinitiation](../1_customer_business_cases/Customer%20INDIVIDUAL/Business%20Cases%20Samples/EV_A1.1_Entity%20Data%20Overwrite%20+%20Scan%20Reinitiation.json) 
1. [Entity Data Scan + Screening ](../1_customer_business_cases/Customer%20INDIVIDUAL/Business%20Cases%20Samples/EV_A2_Entity%20Data%20Scan%20+%20Screening.json)
2. [Entity With Related Entities Scan + Screening](../1_customer_business_cases/Customer%20INDIVIDUAL/Business%20Cases%20Samples/EV_A3_Entity%20With%20Related%20Entities%20Scan%20+%20Screening.json)
3. [Entity Historical Data Transfer](../1_customer_business_cases/Customer%20INDIVIDUAL/Business%20Cases%20Samples/IMP_B1_Entity%20Historical%20Data%20Transfer.json)
4.1. [Entity Historical Data Overwrite](../1_customer_business_cases/Customer%20INDIVIDUAL/Business%20Cases%20Samples/IMP_B1.1_Entity%20Data%20Overwrite.json)
1. [All Fields Payload Example](../1_customer_business_cases/Customer%20INDIVIDUAL/Business%20Cases%20Samples/IMP_C1_All%20Fields%20Payload%20Example.json)

All payload fields & descriptions suitable for customer - `INDIVIDUAL` request - [<u>here</u>](INDIVIDUAL/INDIVIDUAL_FIelds.md).

--- 
>Customer - ORGANIZATION
1. [Entity Data Scan Initiation](../1_customer_business_cases/Customer%20ORGANIZATION/Business%20Cases%20Samples/EV_A1_Entity%20Data%20Scan%20Initiation.json) 
1.1 [Entity Data Overwrite + Scan Reinitiation](../1_customer_business_cases/Customer%20ORGANIZATION/Business%20Cases%20Samples/EV_A1.1_%20Entity%20Data%20Overwrite%20+%20Scan%20Reinitiation.json) 
1. [Entity Data Scan + Screening](../1_customer_business_cases/Customer%20ORGANIZATION/Business%20Cases%20Samples/EV_A2_Entity%20Data%20Scan%20+%20Screening.json)
2. [Entity With Related Entities Scan + Screening](../1_customer_business_cases/Customer%20ORGANIZATION/Business%20Cases%20Samples/EV_A3_Entity%20With%20Related%20Entities%20Scan%20+%20Screening.json)
3. [Entity Historical Data Transfer](../1_customer_business_cases/Customer%20ORGANIZATION/Business%20Cases%20Samples/IMP_B1_Entity%20Historical%20Data%20Transfer.json)
4.1 [Entity Data Overwrite](../1_customer_business_cases/Customer%20ORGANIZATION/Business%20Cases%20Samples/IMP_B1.1_Entity%20Data%20Overwrite.json)
1. [All Fields Payload Example](../1_customer_business_cases/Customer%20ORGANIZATION/Business%20Cases%20Samples/IMP_C1_All%20Fields%20Payload%20Example.json)

All payload fields & descriptions suitable for customer - `ORGANIZATION` request - [<u>here</u>](ORGANIZATION/ORGANIZATION_FIelds.md)

---
## Possible Responses

```json
200 OK
  "resultType": "REQUEST_ACCEPTED"


400 Bad Request
    "resultType": "REQUEST_REJECTED",
    "errorCode": "O001",
    "errorDescription": "CommunicationNumber already used in amlyze"


404 Not Found
    "timestamp": "2024-05-26T16:49:50.237+00:00",
    "status": 404,
    "error": "Not Found",
    "path": "/amlyze-ws-rest/customerr" --> mistake inside the endpoint


500 Internal Server Error
  "resultType": "REQUEST_REJECTED"
  "status": 500,
  "error": "Internal Server Error"
```

---

## Possible Errors | Error Codes

All possible errors can be found [<u>here</u>](cust_possible_errors.md). 



