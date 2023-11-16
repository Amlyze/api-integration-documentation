# Create customer



Customers contain identifying information and KYC data. This section provides information on how to generate a customer using the POST method. The documentation covers all aspects of API requests, including endpoints, responses, possible errors, and a minimalistic request example.

------------


## EndPoint

*swagger UI* `GET /swagger-ui/`

`POST /amlyze-ws-rest/simplified-customer (application/json)`


## Samples
[<b>INDIVIDUAL Fields</b>](INDIVIDUAL/INDIVIDUAL_Fields.md)

* [Evaluate_INDIVIDUAL_Mandatory](INDIVIDUAL/INDIVIDUAL_Samples/INDIVIDUAL_Mandatory.xml) 
* [Evaluate_INDIVIDUAL_Full](INDIVIDUAL/INDIVIDUAL_Samples/INDIVIDUAL_Full.xml)

--- 
[<b>ORGANIZATION Fields</b>](ORGANIZATION\ORGANIZATION_Fields.md) 
* [Evaluate_ORGANIZATION_Mandatory](ORGANIZATION/ORGANIZATION_Samples/ORGANIZATION_Mandatory.xml) 
* [Evaluate_ORGANIZATION_Full](ORGANIZATION/ORGANIZATION_Samples/ORGANIZATION_Full.xml)
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


**Possible errors**

All possible errors can be found [*here*](cust_possible_errors.md)  


------


## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully create a customer. Other fields may be optionally included, as specified in the API documentation.



```json
{
	"communicationNumber": "ComNr_000321",
	"requester": "financial_institution",
	"riskManagementCategory": "FAST",
	"entityType": "INDIVIDUAL",
	"customerExtId": "cust_1232",
	"firstName": "Jose",
	"lastName": "Rodriguez",
	"customerStatus": "ACTIVE"
}
```



