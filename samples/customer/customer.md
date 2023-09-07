# Create customer

Creates Customer profile or updates questionaire, if customer already exists. 

**URL** : `/amlyze-ws-rest/customer`

**METHOD**  `POST`

**Auth required** : NO

**Permissions required** : None

## Mandatory Fields
*The bare minimum - essential data necessary to create a Customer:*

<table>
	<thead>
		<tr>
			<td>
				-
			</td>
			<td>
				Name
			</td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td>
				ENUM <br/><b>[PENDING<br/>**ACTIVE**,<br/>**REJECTED**,<br/>**SUSPENDED**,<br/>**CLOSED**]</b>
			</td>
			<td>
				ENUM <br/><i>[PENDING<br/>**ACTIVE**,<br/>**REJECTED**,<br/>**SUSPENDED**,<br/>**CLOSED**]</i>
			</td>
		</tr>
	</tbody>
</table>

| field | type | mandatory | example | description |
|---|---|---|---|---|
| communicationNumber | String | true | ComNr_000321 | Unique number of communication. used for risk assessment callback |
 customerExtId | String | true| cust_123243| Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution |     
 | action | ENUM <br/>[ **CREATE** (*default*), <br/>**UPDATE**] |false | UPDATE | Element is used to change the data of an existing Customer. </br>❗ NOTE: all data will be replaced with newly received ones |    
 | customerStatus | ENUM <br/>[**PENDING**,<br/>**ACTIVE**,<br/>**REJECTED**,<br/>**SUSPENDED**,<br/>**CLOSED**] | true | PENDING| Customer status represents the current standing or state of a customer's relationship with a business or organization. </br>**PENDING** - Customer application is received,</br>**ACTIVE** - Customer is onboarded ( *account is provided or customer assessment case is resolved*)</br>**REJECTED** - the customer for some reasons was rejected before opening an account for him.</br>**SUSPENDED** - Customer's activities for some reasons are restricted</br>**CLOSED** - Customer's profile is changed to being disabled |           
 | riskManagementCategory | String (*classifier*) | true| IND </br> ORG| Code of risk management category for evaluation of the object </br>💡 Possible values here are given just as an example, in the configuration period these could be updated | 
 | sourceOfRiskLevel | ENUM<br/>[**IMPORT**, <br/>**EVALUATE**] | true | IMPORT | Source of risk level. </br> The value **"EVALUATE"** should be used for normal business processes - <br/>*risk assessment will be performed*</br>The value **"IMPORT"** should be used for migration purposes only – <br/>*the customer and it's questionnaire will be imported without risk assessment* |          
 | riskLevel | ENUM <br/>[**NONE**,<br/>**LOW**,<br/>**MEDIUM**,<br/>**HIGH**,<br/>**EXTREME**] | true/false | NONE | **MANDATORY** when sourceOfRiskLevel = ***IMPORT*** <br/> **NOT MANDATORY** when sourceOfRiskLevel = ***EVALUATE*** |
| entityType | ENUM <br/>[**INDIVIDUAL**,<br/>**ORGANIZATION**] | true | INDIVIDUAL | Whether bussines or individual entity |
| applicationDate | Date | true | 2000-01-03 | Date when customer first applied |
| firstName | String | true/false | John |  **MANDATORY** when entityType = ***INDIVIDUAL*** <br/> **NOT MANDATORY** when entityType = ***ORGANIZATION*** |
| lastName | String | true/false | Andrew |  **MANDATORY** when entityType = ***INDIVIDUAL*** <br/> **NOT MANDATORY** when entityType = ***ORGANIZATION*** |
| birthDate | Date | false | 1995-05-24| Date of birth of individual entity |  
| citizenshipCountry | String | false | LT | Country of citizenship of individual entity |        

#### All fields 
		| Ability to inspect all relevant fields when creating or modifying a customer profile. |
[*ALL FIELDS*](fields.md) 

### Minimalistic request:

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
	"firstName": "Testas",
	"lastName": "Testauskas",
	"birthDate": "2000-05-10",
	"citizenshipCountry": "LT"
}
```



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



