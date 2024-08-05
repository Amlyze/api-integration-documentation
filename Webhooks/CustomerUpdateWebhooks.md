# Customer update webhooks (callbacks)

## Envelope

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Cloudevent representation</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>type</b></td>
            <td>String</td>
            <td>Header: <b>Ce-Type</b></td>
            <td>com.amlyze.customer.&lt;event-type&gt;</td>
            <td>Unique event type. Check documentation below to see available types</td>
        </tr>
        <tr>
            <td><b>specversion</b></td>
            <td>String</td>
            <td>Header: <b>Ce-Specversion</b></td>
            <td>1.0</td>
            <td><a href=https://cloudevents.io/> Cloud Events Specification version that is being used</td>
        </tr>
        <tr>
            <td><b>source</b></td>
            <td>URI-reference<br/><a href="https://datatracker.ietf.org/doc/html/rfc3986#section-4.1">RFC 3986 - Uniform Resource Identifier (URI): Generic Syntax</a></td>
            <td>Header: <b>Ce-Source</b></td>
            <td>customer</td>
            <td>Event source</td>
        </tr>
        <tr>
            <td><b>subject</b></td>
            <td>String</td>
            <td>Header: <b>Ce-Subject</b></td>
            <td>82deaa92-d559-40bd-96b7-053341a08e28</td>
            <td>Event subject represents a resource external id</td>
        </tr>
        <tr>
            <td><b>id</b></td>
            <td>String</td>
            <td>Header: <b>Ce-Id</b></td>
            <td>0412a5ca-3be7-46b7-87de-38366397602e</td>
            <td>Unique event ID</td>
        </tr>
        <tr>
            <td><b>time</b></td>
            <td>Timestamp</td>
            <td>Header: <b>Ce-Time</b></td>
            <td>2019-12-13T12:01:02.694Z</td>
            <td>Event time</td>
        </tr>
        <tr>
            <td><b>datacontenttype</b></td>
            <td>String</td>
            <td>Header: <b>Content-Type</b></td>
            <td>application/json</td>
            <td>Data content type</td>
        </tr>
        <tr>
            <td><b>data</b></td>
            <td>String</td>
            <td>HTTP Request body</td>
            <td></td>
            <td>Event response. Differs on the event type</td>
        </tr>
    </tbody>
</table>

---

## com.amlyze.customer.updated

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>customerExternalID</b></td>
            <td>String</td>
            <td>82deaa92-d559-40bd-96b7-053341a08e28</td>
            <td>Customer external ID</td>
        </tr>
        <tr>
            <td><b>sanctioned</b></td>
            <td>Boolean (optional)</td>
            <td>true</td>
            <td>Customer sanctioned or not</td>
        </tr>
        <tr>
            <td><b>pep</b></td>
            <td>Boolean (optional)</td>
            <td>true</td>
            <td>The customer is/isn't a politically exposed person status</td>
        </tr>
        <tr>
            <td><b>inAdverseMedia</b></td>
            <td>Boolean (optional)</td>
            <td>true</td>
            <td>Customer found in adverse media or not</td>
        </tr>
        <tr>
            <td><b>inInternalList</b></td>
            <td>Boolean (optional)</td>
            <td>true</td>
            <td>Customer found in internal list or not</td>
        </tr>
        <tr>
            <td><b>riskLevel</b></td>
            <td>String (optional)<br/><b>Enum:</b><br/>
[NONE,LOW,MEDIUM,HIGH,EXTREME]</td>
            <td>EXTREME</td>
            <td>Customer risk level</td>
        </tr>
        <tr>
            <td><b>status</b></td>
            <td>String (optional)<br/><b>Enum:</b><br/>
[ACTIVE, PENDING, REJECTED, SUSPENDED, CLOSED]</td>
            <td>ACTIVE</td>
            <td>Customer status in Amlyze system</td>
        </tr>
        <tr>
            <td><b>updatedAt</b></td>
            <td>Timestamp</td>
            <td>2019-12-13T12:01:02.694Z</td>
            <td>Customer status in Amlyze system</td>
        </tr>
    </tbody>
</table>

**Example**

```json
{
  "customerExternalID": "82deaa92-d559-40bd-96b7-053341a08e28",
  "sanctioned": true,
  "pep": true,
  "inAdverseMedia":true,
  "inInternalList":true,
  "riskLevel": "EXTREME",
  "status": "PENDING",
  "updateAt": "2019-12-13T12:01:02.694Z"
}
```
