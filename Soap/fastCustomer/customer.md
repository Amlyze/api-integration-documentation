# Create customer

Customers contain identifying information and KYC data. This section provides information on how to generate a customer using the POST method. The documentation covers all aspects of API requests, including endpoints, responses, possible errors, and a minimalistic request example.

------------


## EndPoint

**swagger** `GET /swagger-ui/`

**URL structure:** `http://[host][port][path][service]`

**Example:** `http://[host]:8878/amlyze-ws/EvaluateCustomerV2Service`

---

## Additional Info

* METHOD ` POST ` 
* Auth required: `NO`
* Content-Type: `text/xml`
---

## Customer conditions
* Providing only Mandatory fields → Minimalistic Customer profile is created
* During <b>IMPORT</b> two additional fields become mandatory:
	* <b>"CustomerStatus" </b> and <b>"RiskLevel"</b>
---

## Customer WorkFlow
* Creating a new customer → <b>"SourceOfRiskLevel"</b> = `EVALUATE`
* Creating a customer with historical data → <b>"SourceOfRiskLevel"</b> = `IMPORT`
* Adding additional information for already created Customer → <b>"Action"</b> = `UPDATE`
	*With each API call, all newly submitted data for existing customer will be overwritten.
* After Customer is created → Add an Account for him  (More about Accounts → [<b>Here</b>](../account/account.md))
---

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md) 

## Samples
[<b>INDIVIDUAL Fields</b>](INDIVIDUAL/INDIVIDUAL_Fields.md)

* [Evaluate_INDIVIDUAL_Mandatory](INDIVIDUAL/INDIVIDUAL_Samples/evaluate_INDIVIDUAL_Mandatory.xml) 
* [Evaluate_INDIVIDUAL_Full](INDIVIDUAL/INDIVIDUAL_Samples/evaluate_INDIVIDUAL_Full.xml)
* [Import_INDIVIDUAL_Full_Related_IND](INDIVIDUAL/INDIVIDUAL_Samples/import_INDIVIDUAL_Full_Related_IND.xml)

--- 
[<b>ORGANIZATION Fields</b>](ORGANIZATION\ORGANIZATION_Fields.md) 
* [Evaluate_ORGANIZATION_Mandatory](ORGANIZATION/ORGANIZATION_Samples/evaluate_ORGANIZATION_Mandatory.xml) 
* [Evaluate_ORGANIZATION_Full](ORGANIZATION/ORGANIZATION_Samples/evaluate_ORGANIZATION_Full.xml)
* [Import_ORGANIZATION_Full_Related_IND](ORGANIZATION/ORGANIZATION_Samples/import_ORGANIZATION_Full_Related_IND.xml)
* [Import_ORGANIZATION_Full_Related_ORG/IND](ORGANIZATION/ORGANIZATION_Samples/import_ORGANIZATION_Full_Related_ORG_IND.xml)
----------------------

## Expected Response from your system

**<span style="color: green;">"Accepted request"</span>**

`If request was sent correctly, the <Result> displays  <ResultType> together with <CommunicationStatus>`

<table>
		<thead>
			<tr>
				<td ><b>XML TAG<b></td>
				<td ><b>TYPE<b></td>
				<td ><b>DESCRIPTION<b></td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><b>ResultType<b></td>
				<td style="text-align:center">String</br>Enum:</br>
[REQUEST_ACCEPTED]</td>
				<td>Result type returns the answer that the action was successful</td>
			</tr>
			<tr>
				<td><b>CommunicationStatus<b></td>
				<td style="text-align:center">String</br>Enum:</br>
[COMPLETED]</td>
				<td>Indicates that Communication was successful</td>
		</tbody>
</table>

**Example:**
`STATUS: 200 OK`
```xml
<ns2:Result xmlns:ns2="urn:amlyze-services:EvaluateOperationService_v2r0">
            <ns2:ResultType>REQUEST_ACCEPTED</ns2:ResultType>
            <ns2:CommunicationStatus>COMPLETED</ns2:CommunicationStatus>
        </ns2:Result>
```
---
**<span style="color: red;">"Rejected request"</span>**

`If the request was sent not properly, the <Result> displays more information.`

<table>
		<thead>
			<tr>
				<td ><b>XML TAG<b></td>
				<td ><b>TYPE<b></td>
				<td ><b>DESCRIPTION<b></td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><b>ResultType<b></td>
				<td style="text-align:center"> String</br>Enum:</br>
[REQUEST_REJECTED]</td>
				<td>Result type returns the answer that the action was not successful</td>
			</tr>
			<tr>
				<td><b>CommunicationStatus<b></td>
				<td style="text-align:center">String</br>Enum:</br>
[INVALID]</td>
				<td>"INVALID" Communication status can be received when some errors or mistakes occur</td>
            </tr>
            <tr>
				<td><b>ErrorCode<b></td>
				<td style="text-align:center">String</td>
				<td>Error code returns the code of an error</td>
            </tr>
            <tr>
				<td><b>ErrorDescription<b></td>
				<td style="text-align:center">String</td>
				<td>Error is described in a more detailed manner in error description field</td>
            </tr>
		</tbody>
</table>

**Example:**

`STATUS: 400 Bad Request / 500 Internal Server Error`
```xml
<ns2:Result xmlns:ns2="urn:amlyze-services:EvaluateOperationService_v2r0">
            <ns2:ResultType>REQUEST_REJECTED</ns2:ResultType>
            <ns2:CommunicationStatus>INVALID</ns2:CommunicationStatus>
            <ns2:ErrorCode>O001</ns2:ErrorCode>
            <ns2:ErrorDescription>Bad Request</ns2:ErrorDescription>
        </ns2:Result>
```
------


## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully create a customer. Other fields may be optionally included, as specified in the API documentation which that can be found [*here*](fields.md).



```xml
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
    <soap:Body>
        <AMLYZE_CUSTOMER xmlns="urn:amlyze-services:EvaluateCustomerService_v2r0">
            <CommunicationNumber>ComNr_001</CommunicationNumber>
            <Requester>Bank system</Requester>
            <RiskManagementCategory>ORG_PK</RiskManagementCategory>
            <SourceOfRiskLevel>EVALUATE</SourceOfRiskLevel>
            <CustomerExtId>Cust_4541</CustomerExtId>
            <EntityType>ORGANIZATION</EntityType>
            <ApplicationDate>2023-09-15</ApplicationDate>
            <Title>BitBit</Title>
            <RegistrationCountry>LT</RegistrationCountry>
            <LegalForm>COOPERATIVE</LegalForm>
        </AMLYZE_CUSTOMER>
    </soap:Body>
</soap:Envelope>
```




