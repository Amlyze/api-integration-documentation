# api-integration-documentation

## Introduction

To start using Amlyze you need to provide customers, accounts and operations.

Customer contain identifying information and KYC data like declared turnover

Accounts used to identify customers in operationParties

*swagger UI* `GET /swagger-ui/`

*api-doc* `GET /v2/api-docs`



## Endpoints

* [Customer](customer/customer.md) : `POST /amlyze-ws/EvaluateCustomerV2Service`
* [Account](account/account.md) : `POST /amlyze-ws/ImportAccountV2Service`
* [Operation](operation/operation.md) : `POST /amlyze-ws/EvaluateOperationV2Service`

## Classifiers

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
