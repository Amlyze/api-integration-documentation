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
## Customer

Is the first step in creating a customer, which is necessary for all subsequent operations in the API.

<b>Endpoints</b>

* `POST /amlyze-ws-rest/customer`
* `POST /amlyze-ws-rest/validate-batch-customers`
* `POST /amlyze-ws-rest/batch-customers`

> Click [here](customer/README.md)  to move to <b>Customer</b> page

    
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

<b>Endpoints</b>

* `POST /amlyze-ws-rest/account`
* `POST /amlyze-ws-rest/validate-batch-accounts`
* `POST /amlyze-ws-rest/batch-accounts`


> Click [here](account/README.md)  to move to <b>Account</b> page


<b>Used for:</b>
* Creating a new account for the customer
* Updating data of the account
* Preparing customer for the operations

---

## Account balances
The second step. Page provides API fields for adding accounts to the customers

<b>Endpoints</b>

* `PUT /amlyze-ws-rest/account-balance (application/json)`
* `POST /amlyze-ws-rest/batch-account-balances (application/json)`
* `POST /amlyze-ws-rest/validate-batch-account-balances (application/json)`


> Click [here](./accountBalance/README.md) to move to <b>account balance details</b> page

---

## Operations
The Grand Final. Comprehensive overview of operation types, conditions, and workflows

<b>Endpoints</b>

* `POST /amlyze-ws-rest/operation`
* `POST /amlyze-ws-rest/validate-batch-operations`
* `POST /amlyze-ws-rest/batch-operations`

> Click [here](operation/README.md) to move to <b>Operation</b> page


<b>Used for:</b>
* Creating-importing operations with Historical data
* Creating-evaluating operations with KYC evaluation
* Checking  every possible type of operation
* Checking the conditions and workflows for every Operation type.
* Checking responses from your system
* Checking Callbacks (Webhooks)
---

## Contract

<b>Endpoints</b>

* `POST /amlyze-ws-rest/contract`
* `PUT /amlyze-ws-rest/contract`
* `POST /amlyze-ws-rest/validate-batch-contracts`
* `POST /amlyze-ws-rest/batch-contracts`

 > Click [here](contract/README.md) to move to <b>Contract</b> page

<b>Used for:</b>
* Creating a new contract for the customer
* Updating data of the contract

---

## Simplified Customer

<b>Endpoint</b>

* `POST /amlyze-ws-rest/simplified-customer`

> Click [here](simplifiedCustomer/README.md) to move to <b>Simplified Customer</b> page


<b>Used for:</b>
* Creating a simplified customer profile


## Classifiers

<b>Endpoint</b>

* `GET /classifier/classifierValue`


 > Click [here](../Classifiers/classifiers.md) to move to <b>Classifiers</b> page 
  

* classifierValue   - a particular classifier should be placed
