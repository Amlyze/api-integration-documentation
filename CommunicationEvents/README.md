# Introducing Communication Events: Streamline Your Data Flow with Real-Time events REST API

<p>
Communication events are a versatile REST API designed to simplify communication event management and streamline data flow within your systems. 
With functionality akin to webhooks but with added flexibility, communication events empowers you to effortlessly manage and track 
events in real-time, ensuring seamless data synchronization across your applications if webhooks does not respond properly.
</p>

<p>
With communication events, you gain unprecedented control over your communication processes, allowing you to monitor pending or completed events with ease. 
</p>

## Integration and details

`GET https://[host]:[port]/api/integration-services/v1/communications-events/{communicationNumber}`

### Request response

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
			<td><b>events</b></td>
			<td><a href="#EventData">EventData[]</a></td>
			<td>
                Events data.
            </td>
		</tr>
		<tr>
			<td><b>errors</b></td>
			<td><a href="#ErrorMessage">ErrorMessage[]</a></td>
			<td>Name of the system requesting web service</td>
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

### EventData

> Check related pages for events envelopes and events payloads details.

* [Risk management events](riskManagementEvents.md)
* [Screening event](screeningEvents.md)


## Example

```json
{
  "events": [
    {
      "type": "app.amlyze.customer.riskmanagement.kyc_scoring.completed",
      "source": "2023-06-02T07:24:51.387Z",
      "subject": "extid",
      "data": {
        "initialRiskLevel": "MEDIUM",
        "finalRiskLevel": "MEDIUM",
        "decisionType": "ACCEPTED",
        "approvedAt": "2023-06-11T21:00:00.000Z"
      }
    }
  ],
  "errors": [
    {
        "code": "INTERNAL_SERVER_ERROR",
        "description": "Internal server error"
    },
    {
      "code": "BAD_REQUEST",
      "description": "Communication number is required"
    }
  ]
}
```