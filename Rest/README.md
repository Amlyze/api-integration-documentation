# api-integration-documentation

---
## REST Introduction

API documentation section covers how to manage the integration and make API requests for the best practise of accessing AMLYZE.

---

*swagger UI* `GET /swagger-ui/`

*api-doc* `GET /v2/api-docs`

---
## API Usage

The endpoints for different requests will slightly differ, but the structure of each endpoint remains the same.

URL structure: `https://[host][port][path][service]`

---
###Customer

<b>Endpoint</b>

* [Customer](customer/customer.md) : `POST /amlyze-ws-rest/customer`
    * Is the first step in creating a customer, which is necessary for all subsequent operations in the API. 

<b>Used for:</b>
* Checking customers against sanctions lists
* Creating - <i>importing</i> customers with historical data
* Creating - <i>evaluating</i> customers with KYC evaluation
* Updating customer profiles (Individual or Organization)
* Checking the conditions, fields and workflow for Customers
* Checking responses from your system
* Checking Callbacks (Webhooks)
---
###Account
<b>Endpoint</b>

* [Account](account/account.md) : `POST /amlyze-ws-rest/account`
    * The second step, provides API fields for adding customer accounts


<b>Used for:</b>
* Creating a new account for the customer
* Updating data of the account
* Preparing customer for the operations

---

###Operations
<b>Endpoint</b>

* [Operation](operation/operation.md) : `POST /amlyze-ws-rest/operation`
    * The Grand Final, comprehensive overview of operation types, conditions, and workflows

<b>Used for:</b>
* Creating-importing operations with Historical data
* Creating-evaluating operations with KYC evaluation
* Checking  every possible type of operation
* Checking the conditions and workflows for every Operation type.
* Checking responses from your system
* Checking Callbacks (Webhooks)
---
---
## Classifiers

Classifiers guide you through extracting needed values for upcoming request fields

---

METHOD: `GET`
Auth required: `NO`
Permissions required: `None`

---

 `{{baseUrl}}/classifier/classifierValue`
 * {{baseUrl}}- provided IP address that was given by the Amlyze
 * classifierValue   - a particular classifier provided below should be placed

 
<b>Example:</b> `https://{{host}}:8878/classifier/riskManagementCategory`

---

* `GET /classifier/relationType`
* `GET /classifier/accountType`
* `GET /classifier/activityType`
* `GET /classifier/appealReasonType`
* `GET /classifier/serviceType`
* `GET /classifier/legalForm`
* `GET /classifier/serviceType`
* `GET /classifier/legalForm`
* `GET /classifier/incomeSourceType`
* `GET /classifier/sourceOfWealth`
* `GET /classifier/currency`
* `GET /classifier/country`
* `GET /classifier/decisionGround`
* `GET /classifier/operationType`
* `GET /classifier/fnttOperationType`
* `GET /classifier/fnttReportType`
* `GET /classifier/fnttSuspicionCriteria`
* `GET /classifier/introductionSourceType`
* `GET /classifier/paymentPurposeType`
* `GET /classifier/managementActionType`
* `GET /classifier/riskManagementCategory`
* `GET /classifier/turnoverType`
* `GET /classifier/addressType`
