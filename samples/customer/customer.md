# Create customer

Creates Customer profile or updates questionaire, if customer already exists. 

**URL** : `/amlyze-ws-rest/customer`

**METHOD**  `POST`

**Auth required** : NO

**Permissions required** : None

**Data constraints** : 

* communicationNumber unique
* customerExtId  identification
* action CREATE/UPDATE 

## Minimalistic request:

```json
{
	"communicationNumber": "testing_001",
	"customerExtId": "testingOperations_001",
	"requester": "AMLYZE",
	"action": "CREATE",
	"customerStatus": "ACTIVE",
	"riskManagementCategory": "IND_PK",
	"sourceOfRiskLevel": "IMPORT",
	"riskLevel": "NONE",
	"entityType": "INDIVIDUAL",
	"applicationDate": "2012-10-01",
	"approvalDate": "2012-10-01",
	"firstName": "Testas",
	"lastName": "Testauskas",
	"nationalCode": "1234567890123",
	"birthDate": "2000-05-10",
	"birthCountry": "LT",
	"citizenshipCountry": "LT"
}
```

possible fields description
[fields.md](fields.md)

**prefilled samples**
* [INDIVIDUAL_ALL_FIELDS](samples%2Fcustomer%2FCustomer_individual_full.json)
* [ORGANIZATION_ALL_FIELDS](samples%2Fcustomer%2FCustomer_Organization_full.json)
* [ORGANIZATION_IND_related_entity](samples%2Fcustomer%2Fcustomer_import_org_indRE.json)
* [ORGANIZATION_ORG_related_entity](samples%2Fcustomer%2Fcustomer_import_org_orgRE.json)



## Success Response

**Condition** : If everything is OK.

**Code** : `202 Accepted`

**Content example**

```json
{
  "resultType": "REQUEST_ACCEPTED"
}
```

## Business ERROR Response

**Condition** : If there are some inconsistencies with data

**Code** : `200 OK`

**Content example**
```json
{
  "resultType": "REQUEST_REJECTED",
  "errorCode": "C004",
  "errorDescription": "Customer already exists"
}
```

### Possible errors

* AV07                         `bad value for TIMESTAMP (format: 'yyyy-MM-dd HH:mm:ss.SSSZ') valueCode: lastonlinesupport`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  CompanyAssetValue`
* C016.I06                     `Problem with field for INDIVIDUAL type customer.  CitizenshipCountry not found in amlyze`
* C008.I02                     `When source of risk level IMPORT.  'Lead' risk management category is forbidden`
* C015.                        `Field not allowed for ORGANIZATION. Field:  LastName`
* SCR01                        `screening process is undefined: NOT_EXISTS`
* Q004.ADR02                   `Problem with Address (index: 0 ). Country is mandatory and must exist in Amlyze`
* C015.                        `Field not allowed for ORGANIZATION. Field:  SecondCitizenshipCountry`
* C017.C016.RE01               `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). Relation type is mandatory`
* Q014.RC01                    `Problem with PaymentCountry (index: 0 ). PaymentCountry not found in Amlyze`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  NumberOfEmployees`
* AV07                         `bad value for BOOLEAN (values: true false') valueCode: isvip`
* C012                         `ApplicationDate is mandatory`
* C002                         `CustomerExtId is mandatory.`
* Q002.DOC06                   `Problem with Customer BusinessEntityDocument index = 0 . DocumentIssueCountry is mandatory and must exist in Amlyze`
* Q017.COTP01                  `CountryOfTaxPayment (index: 0 ). CountryOfTaxPayment not found in Amlyze`
* C007                         `RiskManagementCategory does not exist in Amlyze`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  LicenseDescription`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  NumberOfAudits`
* C015.                        `Field not allowed for ORGANIZATION. Field:  FirstName`
* C017.C016.RE08.DOC03         `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). Problem with BusinessEntityDocuments (index: 0 ). DocumentNumber is mandatory.`
* C016.I08                     `permanentResidenceCountry not defined in Amlyze`
* FOA02                        `PensionCountry is invalid`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  RegionOfActivityDescription`
* C016.I06                     `BirthCountry not defined in Amlyze`
* C013a                        `ClosingDate can not exist for not CLOSED CustomerStatus`
* C013                         `ClosingDate is mandatory for CLOSED CustomerStatus`
* C017.C016.RE08.DOC01         `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). Problem with BusinessEntityDocuments (index: 0 ). EntityType is mandatory. values : INDIVIDUAL, ORGANIZATION`
* C017.C016.RE06.Co2           `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). Problem with Contact (index: 0 ). ContactDetails is mandatory`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  Title`
* AV07                         `bad value for INTEGER valueCode:  number_users`
* C017.O01                     `for ORGANIZATION type customer  Title is mandatory`
* C010                         `EntityType is mandatory.`
* C015.                        `Field not allowed for ORGANIZATION. Field:  PermanentResidenceCountry`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  LegalForm`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  ThirdPartyServicesUsedDescription`
* C015.                        `Field not allowed for ORGANIZATION. Field:  BirthCountry`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  GIIN`
* C017.C016.RE01               `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). Relation type is not defined in Amlyze`
* C004                         `Cannot update not existing customer, use Action = CREATE`
* C017.C016.RE03               `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). Country not defined in Amlyze`
* C017.C016.RE02               `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). EntityType is mandatory.`
* REG                          `registrationCountry must exist in Amlyze`
* C017.C016.RE06.Co1           `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). Problem with Contact (index: 0 ). ContactType is mandatory. values: MOBILEPHONE, FIXEDPHONE, EMAIL, WEBSITE`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  EstablishmentDate`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  PeriodsOfAuditsInYears`
* C017.C016.AV07               `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 1 ). bad value for BOOLEAN (values: true false') valueCode: is_related_to_Lithuania`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  OrganizationalStructureDescription`
* C007                         `RiskManagementCategory is mandatory.`
* C017.C016.RE06.ADR02         `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 0 ). Problem with Address (index: 0 ). AddressType is not defined in amlyze.`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  LEI`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  Title`
* FOA01                        `FieldOfActivity.Student.Country is invalid`
* C016.I08                     `SecondCitizenshipCountry not defined in Amlyze`
* C015.                        `Field not allowed for ORGANIZATION. Field:  FirstName`
* C015.                        `Field not allowed for ORGANIZATION. Field:  CitizenshipCountry`
* C015.                        `Field not allowed for ORGANIZATION. Field:  BirthDate`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  TradingName`
* C017.C016.RE05               `Problem with field for ORGANIZATION type customer.  Problem with relatedEntity (index: 1 ). LegalForm not found in Amlyze`
* C014.                        `Field not allowed for INDIVIDUAL. Field:  ActivityInRestrictedRegionDescription`
* Q009.CA01                    `Problem with CountryOfActivity (index: 1 ). CountryOfActivity not found in Amlyze`



