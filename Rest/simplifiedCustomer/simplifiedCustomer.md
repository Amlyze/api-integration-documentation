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

  ## Additional Info

* METHOD ` POST ` 
* Auth required: `NO`
* Content-Type: `application/json`
---

## Samples
>Simplified Individual API Fields [*here*](INDIVIDUAL/INDIVIDUAL_Fields.md) 

* [Individual Mandatory](INDIVIDUAL/INDIVIDUAL_Samples/individual_Mandatory.json) 
* [Individual Full](INDIVIDUAL/INDIVIDUAL_Samples/individual_Full.json)

--- 

  >Simplified Organization API Fields [*here*](ORGANIZATION/ORGANIZATION_Fields.md) 

* [Organization Mandatory](ORGANIZATION/ORGANIZATION_Samples/organization_Mandatory.json) 
* [Organization Full](ORGANIZATION/ORGANIZATION_Samples/organization_Full.json)
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


-


------


## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully create a Simplified Customer. Other fields may be optionally included, as specified in the API documentation.



```json
{
	{
    "communicationNumber": "ComNr_0048",
    "requester": "AMLYZE_TEST",
    "riskManagementCategory": "OCCASIONAL_CUSTOMER",
    "entityType": "INDIVIDUAL",
    "customerExtId": "IND202311175389",
    "firstName": "Simplified",
    "lastName": "Mikelangelo"
}
}
```



