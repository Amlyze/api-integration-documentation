# Operation reconciliation service

<p>
Returns all registered operation for given timeframe.
</p>

## Integration and details

`GET https://[host]:[port]/api/integration-services/v1/operations-reconciliation?registeredFrom={registeredFromDate}&registeredTill={registeredTillDate}`

### Request

<table>
	<thead>
		<tr>
			<td><b>Query Parameters</b></td>
            <td><b>Mandatory</b></td>
			<td><b>Type</b></td>
			<td><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>registeredFrom</b></td>
            <td><b>true</b></td>
			<td>
                Timestamp
                Format: ISO 8601
                yyyy-MM-dd'T'HH:mm:ss.SSSX</td>
			<td>
                eg: 2023-08-21T08:07:34.605Z
            </td>
		</tr>
		<tr>
			<td><b>registeredTill</b></td>
 <td><b>false</b></td>
			<td>
                Timestamp
                Format: ISO 8601
                yyyy-MM-dd'T'HH:mm:ss.SSSX</td>
			<td>
                eg: 2023-08-28T08:07:34.605Z
            </td>
		</tr>
</tbody>
</table>


### Response

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>operations</b></td>
			<td>Operation[]</td>
			<td>
            </td>
		</tr>
		<tr>
			<td><b>errors</b></td>
			<td>ErrorMessage[]</td>
			<td>
            </td>
		</tr>
</tbody>
</table>

### Operation

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>extId</b></td>
			<td>String</td>
			<td>ext id of operation</td>
		</tr>
		<tr>
			<td><b>businessUnit</b></td>
			<td>String</td>
			<td>businessUnit that operation belongs to </td>
		</tr>
</tbody>
</table>


### ErrorMessage

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>code</b></td>
			<td>String</td>
			<td>Error code</td>
		</tr>
		<tr>
			<td><b>description</b></td>
			<td>String</td>
			<td>Error description</td>
		</tr>
</tbody>
</table>



## Example

```json
{
  "operations": [
    {
      "extId": "testingqwe",
      "businessUnit": "businessUnit1"
    },
    {
      "extId": "testingqweqwe",
      "businessUnit": "businessUnit2"
    }
  ]
}
```

```json
{
  "errors": [
    {
      "code": "BAD_REQUEST",
      "description": "RegisteredFrom must be before registeredTill"
    }
  ]
}
```
