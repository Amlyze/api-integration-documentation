# Create customer



Customers contain identifying information and KYC data. This section provides information on how to generate a customer using the POST method. The documentation covers all aspects of API requests, including endpoints, responses, possible errors, and a minimalistic request example.

------------


## EndPoints

*swagger* `GET /swagger-ui/`

`POST /amlyze-ws-rest/customer (application/json)`

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md) 

**Samples**
* [INDIVIDUAL_All_Fields](samples%2Fcustomer%2FCustomer_individual_full.json)
* [ORGANIZATION_All_Fields](samples%2Fcustomer%2FCustomer_Organization_full.json)
* [INDIVIDUAL_IND_related_entity](samples%2Fcustomer%2Fcustomer_import_ind_indRE.json)
* [ORGANIZATION_IND_related_entity](samples%2Fcustomer%2Fcustomer_import_org_indRE.json)
* [ORGANIZATION_ORG_related_entity](samples%2Fcustomer%2Fcustomer_import_org_orgRE.json)

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
					<pre><b>{
  "resultType": "REQUEST_ACCEPTED"
}
				</td>
			</tr>
			<tr>
				<td><b>400<b></td>
				<td style="text-align:center"><i>Bad Request<i></td>
				<td> <pre><b>{
"errors": [
        "CommunicationNumber is mandatory"
   	]
}
				</td>
			</tr>
				<tr>
				<td><b>404<b></td>
				<td style="text-align:center"><i>Not Found<i></td>
				<td> <pre><b>{
  "resultType": "REQUEST_REJECTED",
  "status": 404,
  "error": "Not Found"
}
				</td>
			</tr>
			<tr>
				<td><b>500<b></td>
				<td style="text-align:center"><i>Internal Server Error<i></td>
				<td> <pre><b>{
  "resultType": "REQUEST_REJECTED"
  "status": 500,
  "error": "Internal Server Error"
}
				</td>
			</tr>
		</tbody>
</table>


**Possible errorrs**

All possible errors can be found [*here*](cust_possible_errors.md)  


------


## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully create a customer. Other fields may be optionally included, as specified in the API documentation which that can be found [*here*](fields.md).



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




