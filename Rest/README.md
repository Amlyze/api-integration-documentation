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

<b>Endpoint</b>

* `POST /amlyze-ws-rest/customer`

> Click [here](customer/customer.md)  to move to <b>Customer</b> page

    
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

<b>Endpoint</b>

* `POST /amlyze-ws-rest/account`


> Click [here](account/account.md)  to move to <b>Account</b> page


<b>Used for:</b>
* Creating a new account for the customer
* Updating data of the account
* Preparing customer for the operations

---

## Operations
The Grand Final. Comprehensive overview of operation types, conditions, and workflows

<b>Endpoint</b>

* `POST /amlyze-ws-rest/operation`

> Click [here](operation/operation.md) to move to <b>Operation</b> page


<b>Used for:</b>
* Creating-importing operations with Historical data
* Creating-evaluating operations with KYC evaluation
* Checking  every possible type of operation
* Checking the conditions and workflows for every Operation type.
* Checking responses from your system
* Checking Callbacks (Webhooks)
---

## Contract

<b>Endpoint</b>

 * `POST /amlyze-ws-rest/contract`

 > Click [here](contract/contract.md) to move to <b>Contract</b> page

<b>Used for:</b>
* Creating a new contract for the customer
* Updating data of the contract

---

## Simplified Customer

<b>Endpoint</b>

* `POST /amlyze-ws-rest/simplified-customer`

> Click [here](simplifiedCustomer/simplifiedCustomer.md) to move to <b>Simplified Customer</b> page


<b>Used for:</b>
* Creating a simplified customer profile


## Classifiers

<b>Endpoint</b>

* `GET /classifier/classifierValue`


 > Click [here](../Classifiers/classifiers.md) to move to <b>Classifiers</b> page 
  

* classifierValue   - a particular classifier should be placed