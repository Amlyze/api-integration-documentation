# Create customer



Customers contain identifying information and KYC data. This section provides information on how to generate a customer using the POST method. The documentation covers all aspects of API requests, including endpoints, responses, possible errors, and a minimalistic request example.

------------


## EndPoints

*swagger UI* `GET /swagger-ui/`

`POST /amlyze-ws-rest/customer (application/json)`


## Samples

To check all possible API fields for `INDIVIDUAL`, click [<b>here</b>](INDIVIDUAL/INDIVIDUAL_FIelds.md)

* [Evaluate Mandatory](INDIVIDUAL/INDIVIDUAL_Samples/evaluate_Mandatory.json) 
* [Import Mandatory](INDIVIDUAL/INDIVIDUAL_Samples/import_Mandatory.json) 
* [Import Fully Updated](INDIVIDUAL/INDIVIDUAL_Samples/import_Update_Full.json)
* [Evaluate Full with Related Entities](INDIVIDUAL/INDIVIDUAL_Samples/evaluate_Full_RelatedEntities.json)
* [Screening Individual](INDIVIDUAL/INDIVIDUAL_Samples/screening_Individual.json)
--- 
To check all possible API fields for `ORGANIZATION`, click [<b>here</b>](ORGANIZATION/ORGANIZATION_FIelds.md)
* [Evaluate Mandatory](ORGANIZATION/ORGANIZATION_Samples/evaluate_Mandatory.json) 
* [Import Mandatory](ORGANIZATION/ORGANIZATION_Samples/import_Mandatory.json) 
* [Import Fully Updated](ORGANIZATION/ORGANIZATION_Samples/import_Update_Full.json)
* [Evaluate Full with Related Entities](ORGANIZATION/ORGANIZATION_Samples/evaluate_Full_RelatedEntities.json)
* [Screening Organization](ORGANIZATION/ORGANIZATION_Samples/screening_Organization.json)

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
"errors": [
        "CommunicationNumber is mandatory"
   	]
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
    "communicationNumber": "ComNr_0021",
    "requester": "financial_institution",
    "riskManagementCategory": "IND_AMLYZE",
    "sourceOfRiskLevel": "EVALUATE",
    "customerExtId": "IND20231113T180927",
	"entityType": "INDIVIDUAL",
	"applicationDate": "2012-10-01",
	"firstName": "Geli",
	"lastName": "Deliono",
    "birthDate": "1995-05-24",
    "citizenshipCountry": "LT"
}
```




