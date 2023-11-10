# api-integration-documentation

## SOAP Introduction

API documentation section covers how to manage the integration and make API requests for the best practise of accessing AMLYZE.

---

*swagger UI* `GET /swagger-ui/`

*api-doc* `GET /v2/api-docs`

---
## API Usage

The endpoints for different requests will slightly differ, but the structure of each endpoint remains the same.

URL structure: `https://[host][port][path][service]`

---
## Customer
Is the first step in creating a customer, which is necessary for all subsequent operations in the API. 
<b> Press [here](customer/customer.md) and move to Customer API page  </b>

<b>Endpoint</b>

 * `POST /amlyze-ws/EvaluateCustomerV2Service`

<b>Used for:</b>
* Checking customers against sanctions lists
* Creating - <i>importing</i> customers with historical data
* Creating - <i>evaluating</i> customers with KYC evaluation
* Updating customer profiles (Individual or Organization)
* Checking the conditions, fields and workflow for Customers
* Checking responses from your system
* Checking Callbacks (Webhooks)
---

## Account
 The second step. Page provides API fields for adding accounts to the customers
<b>Press [here](account/account.md) and move to Account API page</b>

<b>Endpoint</b>

* `POST /amlyze-ws/ImportAccountV2Service`

<b>Used for:</b>
* Creating a new account for the customer
* Updating data of the account
* Preparing customer for the operations

---

## Operations
 The Grand Final. Comprehensive overview of operation types, conditions, and workflows
   <b> Press [here](operation/operation.md) and move to Operation API page </b>

<b>Endpoint</b>

* `POST /amlyze-ws/EvaluateOperationV2Service`


<b>Used for:</b>
* Creating-importing operations with Historical data
* Creating-evaluating operations with KYC evaluation
* Checking  every possible type of operation
* Checking the conditions and workflows for every Operation type.
* Checking responses from your system
* Checking Callbacks (Webhooks)
---

## Leads
* If a customer is not approved to be a customer yet - this is the API you need

<b>Endpoint</b>

* [Leads](leads/leads.md) : `POST /amlyze-ws/EvaluateCustomerV2Service`

    

<b>Used for:</b>
* Creating - evaluating a lead 
* Updating a lead to become a Customer
* Checking responses from your system
* Checking Callbacks (Webhooks)
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
