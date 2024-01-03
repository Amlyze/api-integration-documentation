# api-integration-documentation

## SOAP Introduction
>
> [!CAUTION]
> **SOAP API is deprecated**. We recommend migrating to [REST API](../Rest/README.md).

API documentation section covers how to manage the integration and make API requests for the best practise of accessing AMLYZE.

---

## API Usage

The endpoints for different requests will slightly differ, but the structure of each endpoint remains the same.

URL structure: `https://[host][port][path][service]`

---

## Customer

Is the first step in creating a customer, which is necessary for all subsequent operations in the API.
**Press [here](customer/customer.md) and move to Customer API page**

**Endpoint**

* `POST /amlyze-ws/EvaluateCustomerV2Service`

**Used for:**

* Checking customers against sanctions lists
* Creating - *importing* customers with historical data
* Creating - *evaluating* customers with KYC evaluation
* Updating customer profiles (Individual or Organization)
* Checking the conditions, fields and workflow for Customers
* Checking responses from your system
* Checking Callbacks (Webhooks)

---

## Account

 The second step. Page provides API fields for adding accounts to the customers
**Press [here](account/account.md) and move to Account API page**

**Endpoint**

* `POST /amlyze-ws/ImportAccountV2Service`

**Used for:**

* Creating a new account for the customer
* Updating data of the account
* Preparing customer for the operations

---

## Operations

 The Grand Final. Comprehensive overview of operation types, conditions, and workflows
   **Press [here](operation/operation.md) and move to Operation API page**

**Endpoint**

* `POST /amlyze-ws/EvaluateOperationV2Service`

**Used for:**

* Creating-importing operations with Historical data
* Creating-evaluating operations with KYC evaluation
* Checking  every possible type of operation
* Checking the conditions and workflows for every Operation type.
* Checking responses from your system
* Checking Callbacks (Webhooks)

---

## Leads

* If a customer is not approved to be a customer yet - this is the API you need

**Endpoint**

* [Leads](leads/leads.md) : `POST /amlyze-ws/EvaluateCustomerV2Service`

**Used for:**

* Creating - evaluating a lead
* Updating a lead to become a Customer
* Checking responses from your system
* Checking Callbacks (Webhooks)

---

## Simplified Customer

**Endpoint**

* [Simplified Customer](simplifiedCustomer/simplifiedCustomer.md) : `POST /amlyze-ws-rest/simplified-customer`

**Used for:**

* Creating a simplified customer profile

## Classifiers

**Endpoint**

* [Classifiers](../Classifiers/classifiers.md)  `GET /classifier/<classifierValue>`
  
> classifierValue - a particular classifier should be placed

---

* `GET /classifier/relationType`
* `GET /classifier/accountType`
* `GET /classifier/activityType`
* `GET /classifier/appealReasonType`
* `GET /classifier/businessunit`
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
