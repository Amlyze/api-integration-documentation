# Create Simplified Customer


## Information to know

>Simplified Customer API contains less Mandatory fields than a regular [*Customer*](../customer/customer.md),
therefore workflows for these two separate servers differ.

* Simplified customers contain a minimum ammount of identifying information and KYC data;
* If needed - Simplified customers goes through <b>Screening</b> workflow;
* Simplified Customer can be updated to become a regular Customer;
* Regular Customer cannot be downgraded to a Simplified Customer;
  
---
><b>OCCASIONAL_CUSTOMER</b> - client without a contract, not a financial institution but service is still provided 

---
 
 This section provides information on how to generate a Simflified Customer using the POST method. The documentation covers all aspects of API requests, including endpoints, responses, possible errors, and a minimalistic request example.

------------


## EndPoint

*swagger UI* `GET /swagger-ui/`

`POST /amlyze-ws-rest/simplified-customer (application/json)`

---

## Additional Info

* METHOD ` POST ` 
* Auth required: `NO`
* Content-Type: `text/xml`
---

## Samples
>Simplified Individual API Fields [*here*](INDIVIDUAL/INDIVIDUAL_Fields.md) 

* [Individual Mandatory](../simplifiedCustomer/INDIVIDUAL/INDIVIDUAL_Samples/individual_Mandatory.xml) 
* [Individual Full](../simplifiedCustomer/INDIVIDUAL/INDIVIDUAL_Samples/individual_Full.xml)

--- 

>Simplified Organization API Fields [*here*](ORGANIZATION/ORGANIZATION_Fields.md) 

* [Organization Mandatory](../simplifiedCustomer/ORGANIZATION/ORGANIZATION_Samples/organization_Mandatory.xml) 
* [Organization Full](../simplifiedCustomer/ORGANIZATION/ORGANIZATION_Samples/organization_Full.xml)

----------------------

## Responses

<table>
    <thead>
        <tr>
            <td><b>Code</b></td>
            <td><b>Status</b></td>
            <td><b>Response</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>200</b></td>
            <td><i>OK</i></td>
            <td>
                <pre>
{
    "resultType": "REQUEST_ACCEPTED"
}
                </pre>
            </td>
        </tr>
        <tr>
            <td><b>400</b></td>
            <td><i>Bad Request</i></td>
            <td> 
                <pre>
{
    "errors": ["CommunicationNumber is mandatory"]
}
                </pre>
            </td>
        </tr>
            <tr>
            <td><b>404</b></td>
            <td><i>Not Found</i></td>
            <td> 
                <pre>
{
    "resultType": "REQUEST_REJECTED",
    "status": 404,
    "error": "Not Found"
}
                </pre>
            </td>
        </tr>
        <tr>
            <td><b>500</b></td>
            <td><i>Internal Server Error</i></td>
            <td> 
                <pre>
{
    "resultType": "REQUEST_REJECTED"
    "status": 500,
    "error": "Internal Server Error"
}
                </pre>
            </td>
        </tr>
    </tbody>
</table>

---

**Possible errors**

>All possible errors can be found [*here*](simplCust_possible_errors.md)  


## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully create a customer. Other fields may be optionally included, as specified in the API documentation which that can be found [*here*](fields.md).



```xml
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
    <soap:Body>
        <AMLYZE_CUSTOMER xmlns="urn:amlyze-services:EvaluateCustomerService_v2r0">
            <CommunicationNumber>ComNr_000321</CommunicationNumber>
            <Requester>AMLYZE_System</Requester>
            <RiskManagementCategory>OCCASIONAL_CUSTOMER</RiskManagementCategory>
            <EntityType>INDIVIDUAL</EntityType>
            <CustomerExtId>IND20231118878</CustomerExtId>
            <FirstName>Jose</FirstName>
            <LastName>Rodriguez</LastName>
        </AMLYZE_CUSTOMER>
    </soap:Body>
</soap:Envelope>




