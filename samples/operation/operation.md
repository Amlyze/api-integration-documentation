# Operations

adds account to customer profile, used to find customer in operation party

**URL** : `/amlyze-ws-rest/operation`

**METHOD**  `POST`

**Auth required** : NO

**Permissions required** : None

**Data constraints** : 

* at least one operation party account must exist (identified by accountNumber, BIC, Currency)
* communicationNumber must be unique

## Samples

* [import_sepa_incoming.json](samples%2Foperation%2Fimport_sepa_incoming.json)
* [import_sepa_outgoing.json](samples%2Foperation%2Fimport_sepa_outgoing.json)

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