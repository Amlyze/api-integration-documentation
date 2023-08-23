# register account to customer

adds account to customer profile, used to find customer in operation party

**URL** : `/amlyze-ws-rest/account`

**METHOD**  `POST`

**Auth required** : NO

**Permissions required** : None

**Data constraints** : 

* businessEntityExtId must exist (customer imported/evaluated)
* communicationNumber must be unique



```json
{
  "communicationNumber": "TESTING_002",
  "requester": "AMLYZE",
  "accountExtId": "testingOperations_001",
  "accountNumber": "testingOperations_001",
  "accountPurpose": "accountPurpose",
  "accountStatus": "ACTIVE",
  "accountType": "ORG_B2C",
  "bankTitle": "GOOD BANK",
  "bic": "TEST",
  "businessEntityExtId": "testingOperations_001",
  "currencyCode": "EUR",
  "isOtherFinInstAccount": true,
  "openingDate": "2023-08-21T08:07:34.605Z"
}
```


## Success Response

**Condition** : If everything is OK.

**Code** : `200 OK`

**Content example**

```json
{
  "resultType": "OK"
}
```



## Business ERROR Response

**Condition** : If there are some inconsistencies with data

**Content example**
```json
{
  "resultType": "ERROR",
  "errorDescription": "duplicate communicationNumber"
}
```

### Possible errors

* `AccountExtId is mandatory`
* `AccountNumber is mandatory`
* `BusinessEntityExtId is mandatory`
* `BusinessEntity with given extId does not exist in amlyze`
* `Cannot register account for lead customer`
* `Currency does not exist in Amlyze`
* `Account already linked with other customer`
* `when using external account, bic is mandatory`
* `Given bic does not belong to your institution`
* `openingDate is mandatory`
* `Given AccountType does not exist in Amlyze`
* `CLOSED account requires closingDate`
* `not closed account cant have closing date`