# Account Registration

This section provides detailed information on the endpoints that can be used to create and manage accounts. Accounts are used to uniquely identify customers in operation parties.

---

## EndPoint

**wsdl** `/amlyze-ws/ImportAccountService.wsdl`

**swagger** `GET /swagger-ui/`

**URL structure:** `http://[host][port][path][service]`

**Example:** `http://[host]:8878/amlyze-ws/ImportAccountV2Service`

---

## Additional Info

* METHOD ` POST ` 
* Auth required: `NO`
* Content-Type: `text/xml`
---

## Account conditions
* Field <b>"BusinessEntityExtId"</b>  → identical to a field <b>"CustomerExtId"</b> (<i>provided during  Customer creation)
* Value for <b>"isOtherFinInstAccount"</b>:
	* if <b>True</b> → `BIC` must be provided
	* if <b>False</b> → `BIC`is not needed
---

## Account WorkFlow
* After Account is added → Check whether Customer has Risk Level and Status:
	* If he has → Move to Operations
	* If not → Resolve all "New" generated relevant cases
 * Operations can be initiated ( More about Operations→ [<b>Here</b>](../operation/operation.md)

----

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md)

## Samples

* [account_active](samples/account_active.xml)
* [account_suspended](samples/account_suspended.xml)
* [account_closed](samples/account_closed.xml)
* [account_minimalistic](samples/account_minimalistic.xml)
---

## Expected Response from your system

**<span style="color: green;">"Accepted request"</span>**

`If request was sent correctly, the <Result> displays  <ResultType> together with <CommunicationStatus>`

<table>
		<thead>
			<tr>
				<td><b>XML TAG</b></td>
				<td><b>TYPE</b></td>
				<td><b>DESCRIPTION</b></td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><b>ResultType</b></td>
				<td style="text-align:center">String<br/>Enum:<br/>
[REQUEST_ACCEPTED]</td>
				<td>Result type returns the answer that the action was successful</td>
			</tr>
		</tbody>
</table>

**Example:**

`STATUS: 200 OK`
```xml
<ns2:Result xmlns:ns2="urn:amlyze-services:EvaluateOperationService_v2r0">
            <ns2:ResultType>OK</ns2:ResultType>
        </ns2:Result>
```
---
**<span style="color: red;">"Rejected request"</span>**

`If the request was sent not properly, the <Result> displays more information.`

<table>
		<thead>
			<tr>
				<td><b>XML TAG</b></td>
				<td><b>TYPE</b></td>
				<td><b>DESCRIPTION</b></td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><b>ResultType</b></td>
				<td> String<br/>Enum:<br/>[ERROR]</td>
				<td>Result type returns the answer that the action was not successful</td>
			</tr>
            <tr>
				<td><b>ErrorCode</b></td>
				<td style="text-align:center">String</td>
				<td>Error code returns the code of an error</td>
            </tr>
            <tr>
				<td><b>ErrorDescription</b></td>
				<td style="text-align:center">String</td>
				<td>Error is described in a more detailed manner in error description field</td>
            </tr>
		</tbody>
</table>

**Example:**

`STATUS: 400 Bad Request / 500 Internal Server Error`
```xml
<ns2:Result xmlns:ns2="urn:amlyze-services:EvaluateOperationService_v2r0">
            <ns2:ResultType>ERROR</ns2:ResultType>
            <ns2:ErrorCode>500</ns2:ErrorCode>
            <ns2:ErrorDescription>Error: failed Processing account</ns2:ErrorDescription>
        </ns2:Result>
```
----
**Possible errorrs**

All possible errors can be found [*here*](acc_possible_errors.md)  


----

## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully add an account. Other fields may be optionally included, as specified in the API documentation which that can be found [*here*](fields.md).

```xml
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
    <soap:Body>
        <AMLYZE_ACCOUNT xmlns="urn:amlyze-services:ImportAccountService_v1r0">
            <CommunicationNumber>ComNr_{{seq}}</CommunicationNumber>
            <Requester>Financial_Bank</Requester>
            <ListAccount>
                <Account>
                    <BusinessEntityExtId>Cust_1145</BusinessEntityExtId>
                    <AccountExtId>Extid_004</AccountExtId>
                    <AccountNumber>LT5630800200000011112</AccountNumber>
                    <CurrencyCode>EUR</CurrencyCode>
                    <isOtherFinInstAccount>false</isOtherFinInstAccount>
                    <OpeningDate>2023-09-16T12:10:11+02:00</OpeningDate>
                    <AccountStatus>ACTIVE</AccountStatus> 
                </Account>
            </ListAccount>
        </AMLYZE_ACCOUNT>
    </soap:Body>
</soap:Envelope>
```


