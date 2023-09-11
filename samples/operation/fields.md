# Operation


| field | type | mandatory | example | description |
|---|---|---|---|---|
| communicationNumber | String | true | ComNr_0011 | Unique number of communication |
| requester | String | true | Branch Name | Name of the system requesting web service |
| operationExtId |String | true | Op_22xx22 | External identifier of operation |
| operationType | String | true | SEPA | Notifies about what kind of operation was performed |
| action | String | false | UPDATE | Element is used to change the data of an existing Customer|
| action | String | false | UPDATE | Element is used to change the data of an existing Customer|
| action | String | false | UPDATE | Element is used to change the data of an existing Customer|
| amount | BigDecimal | true | 1499 | Field for the money amount sent in an operation|
| amountInEuro | BigDecimal | true/ false | 1399 | **MANDATORY** when currency is not *eur* <br/> **NOT MANDATORY** when currency is  *eur*
|cardOperationSubType| String | true/false | CARD_PURCHASE |**MANDATORY** when *operationType* = "**CARD_PAYMENT**" or "**CARD_CASH**" <br/>   *CardOperationSubType code from classifier:*<br/>[*Check CardOperationSubType Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) |
| currency | String | true | EUR | *Currency code from classifier:*</br>  [*Check Currency Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) |
| dateAuthorized | Date | false | 2023-05-10T12:10:11+02:00 | Date and Time of operation |
| dateSettled | Date | false | 2023-05-101T15:10:11+02:00 | Date and Time of operation |
| description | String | true | "Fund Transfer" | The purpose of payment is saved under description.<br/> It is necessary for the operation to be proceeded
| destinationCountry | String <br/> Format:<br/> ***ISO-3166 alpha-2*** | false | LT |  *Country code from classifier:*</br>  [*Check Country Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) |
| euroExchangeRate | BigDecimal | true/false | 0.93 |Euro exchange rate for other than Euro currency<br/> **MANDATORY** when currency is not *eur* <br/> **NOT MANDATORY** when currency is  *eur*<br/> *Currency code from classifier:*</br>  [*Check Currency Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) |
| fastPayment | Boolean | false | *true* | Identification if payment should be processed immediately<br/> *Default value is **false***
| financialFlowDirection | FinancialFlowDirectionApi | true | INCOMING | Refers to the movement of money between entities or accounts.
| initializeScreeningProcesses | List<String> | false | PEP | Defines which lists to check during screening process<br/> *ScreeningList code from classifier:*<br/>[*Check Screening List Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) |
| ipAddress | String | false | xxx.zzz.yyyy.www| The IP address of the operation |
| ipAddressCountry | String <br/> Format:<br/> ***ISO-3166 alpha-2*** | false | LT | Country of an IP address of the operation |
| [ListOperationParty](#operation-party) | List<OperationPartyApi> | true | - | List of entities that belong to one operation|
| merchantCode | String | false | 5541 | External identifier of the seller-mediator |
| merchantCountryCode | String <br/> Format:<br/> ***ISO-3166 alpha-2***| false| US | Seller-mediator code<br/> *Country code from classifier:*</br>  [*Check Country Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) |
| merchantDescription | String | false | "Ecommerce merchants" | Seller-mediator description |
| merchantExtId | String | false| External_0112 | External identifier of the seller-mediator |
| merchantName | String | false | Costco | Name of the seller-mediator |
| operationDateTime | Date <br/> Format:<br/> ***ISO 8601*** | true | 2023-03-16T13:00:00Z | The operation date and time show when the operation proceeded with |
| operationStatus | ENUM<br/>[**EXECUTED**,<br/>**REJECTED**] | true/false | EXECUTED | Either operation was successfully executed, or the operation was rejected |
|riskLevel | ENUM<br/>[**NONE**,<br/>**LOW**,<br/>**MEDIUM**,<br/>**HIGH**,<br/>**EXTREME**] | true/false| LOW | The risk level of imported operation<br/>**MANDATORY** when *sourceOfRiskLEvel* is ***IMPORT*** is not *eur* <br/> **NOT MANDATORY** when sourceOfRiskLEvel* is ***EVALUATE***
| riskManagementCategory | String | true | OP_PK | Code of risk management category of object<br/> Risk Management Category code from classifier:*</br>  [*Check RiskManagementCategory Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) |
| salesPointCode | String | false | 54574 | External code of the sales point | 
| salesPointExtId | String | false | S_extid_0145 | External identifier of the sales point |
| sourceCountry | String <br/> Format:<br/> ***ISO-3166 alpha-2*** | false | LT | Source country informs about where the operation was initiated<br/> *Country code from classifier:*</br>  [*Check Country Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) |
| sourceOfRiskLevel | ENUM<br/>[**EVALUATE**,<br/>**IMPORT**] | true | EVALUATE | **"EVALUATE"** should be used for normal business, process - <br/>*risk assessment will be performed*<br/> **"IMPORT"** should be used for migration purposes only -<br/> *operaton will be imported without risk assessment*
|terminalCode| String | false | 57455 | External code of terminal|
|terminalExtId| String | false | t_extid_145 | External identifier of the terminal|


listOperationParty: #Operation-Party

# Operation Party

At least one operation party account must exist in Amlyze (identified by accountNumber, BIC, Currency)

| field | type | mandatory | example | description |
|---|---|---|---|---|
| accountNumber | String | true | LT038625979279192518 | Unique account identification number used in performing operations |
| bankTitle | String | false | TBC bank | Title of bank with which the operation is happening |
| bic | String | true | BICXX22 | Bank identifier code for account number
| cardHolderName | String | false | Eduardo Rodrigues | Data from card |
| cardNumber | String | false | 4720582145647937 | Data from card |
| cardValidTill | String | false | 2025-06-07 | Data from card |
| currency | String | true | GBP | Currency code of operation<br/> *Currency code from classifier:*</br>  [*Check Currency Classifier](https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers) | |
| entityType | ENUM<br/>[**INDIVIDUAL**,<br/>**ORGANIZATION**,<br/>**UNKNOWN**] | true | INDIVIDUAL | Describes client status.<br/>  *UNKNOWN* is valid **only** when *enitytype = counterparty*
| firstName | String | true/false | Eduardo | **MANDATORY** when *entityType* is ***INDIVIDUAL***  <br/> **NOT MANDATORY** when entityType* is ***ORGANIZATION*** or ***UNKNOWN*** |
| lastName | String | true/false | Rodriguez | **MANDATORY** when *entityType* is ***INDIVIDUAL*** <br/> **NOT MANDATORY** when *entityType* is ***ORGANIZATION*** or ***UNKNOWN*** |
| partyRole | ENUM<br/>[**DEBTOR**,<br/>**CREDITOR**,<br/>**ULTIMATE_DEBTOR**,<br/>**ULTIMATE_CREDITOR**] | true | DEBTOR | The role of the party in on-going operation |
| title | String | true/false | TOSHI | **MANDATORY** when *entityType* is ***ORGANIZATION*** or ***UNKNOWN***  <br/> **NOT MANDATORY** when entityType* is ***INDIVIDUAL*** |