# Discard operation service

<p>
Moves operation to archive, operation will not be included in retro processes
</p>

## Integration and details

`DELETE https://[host]:[port]/api/integration-services/v1/discard-operations?extId={operationExtId}&businessUnit={businessUnit}`

### Request

<table>
	<thead>
		<tr>
			<td><b>Query parameters</b></td>
            <td><b>Mandatory</b></td>
			<td><b>Type</b></td>
			<td><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>extId</b></td>
            <td><b>true</b></td>
			<td>String</td>
			<td>
                operation extId 
            </td>
		</tr>
		<tr>
			<td><b>businessUnit</b></td>
            <td><b>false</b></td>
			<td>String</td>
			<td>
                which businessUnit operation belongs to
            </td>
		</tr>
</tbody>
</table>


### Response

200 OK


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


## Response example

```json
{
  "errors": [
    {
      "code": "BAD_REQUEST",
      "description": "Business unit is required"
    }
  ]
}
```
