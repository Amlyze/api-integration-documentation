# Create customer



Customers contain identifying information and KYC data. This section provides information on how to generate a customer using the POST method. The documentation covers all aspects of API requests, including endpoints, responses, possible errors, and a minimalistic request example.

------------


## EndPoints

*swagger* `GET /swagger-ui/`

`POST /amlyze-ws/EvaluateCustomerV2Service (text/xml)`

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md) 

## Samples
[<b>INDIVIDUAL Fields</b>](INDIVIDUAL/INDIVIDUAL_Fields.md)

* [Evaluate_INDIVIDUAL_Mandatory](INDIVIDUAL/INDIVIDUAL_Samples/evaluate_INDIVIDUAL_Mandatory.xml) 
* [Evaluate_INDIVIDUAL_Full](INDIVIDUAL/INDIVIDUAL_Samples/evaluate_INDIVIDUAL_Full.xml)
* [Import_INDIVIDUAL_Full_Related_IND](INDIVIDUAL/INDIVIDUAL_Samples/import_INDIVIDUAL_Full_Related_IND.xml)

--- 
[<b>ORGANIZATION Fields</b>](ORGANIZATION/ORGANIZATION_Fields.md)
* [Evaluate_ORGANIZATION_Mandatory](ORGANIZATION/ORGANIZATION_Samples/evaluate_ORGANIZATION_Mandatory.xml) 
* [Evaluate_ORGANIZATION_Full](ORGANIZATION/ORGANIZATION_Samples/evaluate_ORGANIZATION_Full.xml)
* [Import_ORGANIZATION_Full_Related_IND](ORGANIZATION/ORGANIZATION_Samples/import_ORGANIZATION_Full_Related_IND.xml)
* [Import_ORGANIZATION_Full_Related_ORG/IND](ORGANIZATION/ORGANIZATION_Samples/import_ORGANIZATION_Full_Related_ORG_IND.xml)
----------------------

## Responses

<table>
		<thead>
			<tr>
				<td style="text-align:center"><b>Code<b></td>
				<td style="text-align:center"><b>Status<b></td>
				<td style="text-align:center"><b>Response<b></td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><b>200<b></td>
				<td style="text-align:center"><i>OK<i></td>
				<td>
					<pre><b>
				</td>
			</tr>
			<tr>
				<td><b>400<b></td>
				<td style="text-align:center"><i>Bad Request<i></td>
				<td> <pre><b>
				</td>
			</tr>
				<tr>
				<td><b>404<b></td>
				<td style="text-align:center"><i>Not Found<i></td>
				<td> <pre><b>
				</td>
			</tr>
			<tr>
				<td><b>500<b></td>
				<td style="text-align:center"><i>Internal Server Error<i></td>
				<td> <pre><b>
				</td>
			</tr>
		</tbody>
</table>


**Possible errorrs**

All possible errors can be found [*here*](cust_possible_errors.md)  


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




