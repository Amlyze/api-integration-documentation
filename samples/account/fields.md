# Account
​
| field | type | mandatory | example | description |
|---|---|---|---|---|
| accountExtId | String | true | ComNr_0011 | A unique number of communication |
| accountNumber | String | true | Branch Name | Name of the system requesting web service |
| accountPurpose | String | false | PURPOSE_INVEST | The purpose of owning the account in question |
| accountStatus | ENUM <br/>**[ACTIVE, SUSPENDED, CLOSED]** | true | ACTIVE | Refers to the current condition or state of an account |
| accountType | String | false | ORG_B2B | Categorizes accounts by their intended purposes and features |
| bankTitle | String | false |TBC Bank | Formal name of a financial institution |
| bic | String | true/false| BICXX22 | **MANDATORY** when *isOtherFinInstAccount* is ***true*** <br/>**NOT** **MANDATORY** when *isOtherFinInstAccount* is ***false***|
| businessEntityExtId | String | true | ExtId_0012 | External business entity indicator. Refers to the same value used for the <br/>*customerExtId*, which helps to identify external business entity|
| closingDate | Date <br/> Format: *ISO 8601* <br/>*YYYY-MM-DDTHH:mm:ss+hh:mm* | true/false | 2022-12-11T12:10:11+02:00 | Account opening date |
| currencyCode | String | true | EUR | International currency code |
| isOtherFinInstAccount | Boolean | false | *false* | Declaring whether the account belongs to other financial institution |
| openingDate | Date <br/> Format: *ISO 8601* <br/>*YYYY-MM-DDTHH:mm:ss+hh:mm* | true | 2022-12-11T12:10:11+02:00 | Account opening date |
| suspensionReasons | String | false | Security breach investigation in progress | A reason for suspension can be provided only if the account status is SUSPENDED |