# Batch customer service

## Integration and details

<!-- Swagger Ui `GET https://[host]:[port]/swagger-ui/` (in progress) -->

**Authorization** `Basic Auth`/`Bearer Token`


`POST https://[host]:[port]/amlyze-ws-rest/validate-batch-customers (application/json)` Validate batch of customers without saving

`POST https://[host]:[port]/amlyze-ws-rest/batch-customers (application/json)` Validate batch of customers with saving


> ⚠️ **Warning**: Customers evaluation and screening not available in this service.

The minimalistic request represents customer with the minimum required fields.

```json lines
{
  "customers":[
    {
      "communicationNumber" : "IndividualComNumber0",
      "requester" : "Company Name Amlyze",
      "action" : "CREATE",
      "riskManagementCategory": "IND",
      "customerExtId" : "IndividualExtId0",
      "customerStatus" : "ACTIVE",
      "entityType" : "INDIVIDUAL",
      "applicationDate": "2023-10-01",
      "firstName" : "Tomas",
      "lastName" : "Garcia",
      "citizenshipCountry" : "LT"
    },
    {
      "communicationNumber" : "OrganizationComNumber0",
      "requester" : "Company Name Amlyze",
      "action" : "CREATE",
      "riskManagementCategory" : "ORG",
      "entityType" : "ORGANIZATION",
      "customerExtId" : "OrganizationExtId0",
      "customerStatus" : "ACTIVE",
      "applicationDate" : "2024-04-08T10:45:00.000+02:00",
      "title" : "LTD 'Bull'",
      "registrationCountry" : "LV",
      "legalForm" : "LTD"
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
      "communicationNumber": "IndividualComNumber0",
      "customerExtId": "IndividualExtId0",
      "businessUnit": "businessUnit0",
      "timeElapsedMs": 203
    },
    {
      "resultType": "REQUEST_ACCEPTED",
      "communicationNumber": "OrganizationComNumber0",
      "customerExtId": "OrganizationExtId0",
      "businessUnit": "businessUnit1",
      "timeElapsedMs": 203
    },
  ],
  "timeElapsedMs": 408
}

200 OK
{
  "resultType": "REQUEST_ACCEPTED",
  "results": [
    {
      "resultType": "REQUEST_ACCEPTED",
      "communicationNumber": "IndividualComNumber0",
      "customerExtId": "IndividualExtId0",
      "businessUnit": "businessUnit0",
      "timeElapsedMs": 203
    },
    {
      "resultType": "REQUEST_REJECTED",
      "communicationNumber": "OrganizationComNumber0",
      "customerExtId": "OrganizationExtId0",
      "businessUnit": "businessUnit1",
      "errorCode": "O005",
      "errorDescription": "CommunicationNumber already used in amlyze",
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
  "path": "/amlyze-ws-rest/batch-customers"
}

500 Internal Server Error
{
  "errorCode": "500",
  "errorDescription": "Processing failed",
  "timeElapsedMs": 172
}
```

------

## Available customer types

[<b>Individual</b>](./individual/fields.md)

---
[<b>Organization</b>](./organization/fields.md)

---
