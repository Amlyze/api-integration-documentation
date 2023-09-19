# api-integration-documentation

## Introduction

To start using Amlyze you need to provide customers, accounts and operations.

Customer contain identifying information and KYC data like declared turnover

Accounts used to identify customers in operationParties

*swagger UI* `GET /swagger-ui/`

*api-doc* `GET /v2/api-docs`


## Control fields

<b>SourceOfRiskLevel</b> - specify if assessment should be created or risk level provided 

<b>InitializeScreeningProcesses</b> - specify if screening process should be initialized given object 

<b>RiskManagementCategory</b> - specify how object should be handled in Amlyze


## Endpoints

* [Customer](customer/customer.md) : `POST /amlyze-ws-rest/customer`
* [Account](account/account.md) : `POST /amlyze-ws-rest/account`
* [Operation](operation/operation.md) : `POST /amlyze-ws-rest/operation`

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
