# api-integration-documentation

## Introduction

To start using Amlyze you need to provide customers, accounts and operations.

Customer contain identifying information and KYC data like declared turnover

Accounts used to identify customers in operationParties

## Control fields

SourceOfRiskLevel - specify if assessment should be created or risk level provided 

InitializeScreeningProcesses - specify if screening process should be initialized given object 

RiskManagementCategory - specify how object should be handled in Amlyze

## Endpoints

* [Customer](samples/customer/customer.md) : `POST /amlyze-ws-rest/customer`
* [Account](samples/account/account.md) : `POST /amlyze-ws-rest/account`
* [Operation](samples/operation/operation.md) : `POST /amlyze-ws-rest/operation`

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