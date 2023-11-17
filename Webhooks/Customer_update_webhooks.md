# Customer update webhooks (callbacks)
**`Work In Progress`**

> Events for tracking customer data changes in the system.

## Customer update events
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
            <td><b>type</b></td>
            <td>String</td>
            <td>"com.amlyze.someevent"</td>
            <td>Unique event type</td>
        </tr>
        <tr>
            <td><b>specversion</b></td>
            <td>String</td>
            <td>"1.0"</td>
            <td>Versions</td>
        </tr>
        <tr>
            <td><b>source</b></td>
            <td>URI-reference</br><b>Enum:</b></br>[customer]</br><a href="https://datatracker.ietf.org/doc/html/rfc3986#section-4.1">FC 3986 - Uniform Resource Identifier (URI): Generic Syntax</a></td> 
            <td>"customer"</td>
            <td>Event source</td>
        </tr>
        <tr>
            <td><b>subject</b></td>
            <td>String</td>
            <td>"customerExtId"</td>
            <td>Event subject represents a resource external id</td>
        </tr>
        <tr>
            <td><b>id</b></td>
            <td>String</td>
            <td>"1234-1234-1234"</td>
            <td>Generate a new unique value, e.g. a UUID</td>
        </tr>
        <tr>
            <td><b>time</b></td>
            <td>Timestamp</td>
            <td>"2018-04-05T17:31:00Z"</td>
            <td>Event time</td>
        </tr>
        <tr>
            <td><b>datacontenttype</b></td>
            <td>String</td>
            <td>"application/json"</td>
            <td>Data content type</td>
        </tr>
        <tr>
            <td><b>data</b></td>
            <td>String</td>
            <td></td>
            <td>Event response. Differs on the event type.</td>
        </tr>
    </tbody>
</table>    

---

## Customer update data

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
            <td><b>sanctioned</b></td>
            <td>Boolean (optional)</td>
            <td>true</td>
            <td>Customer sanctioned or not</td>
        </tr>
        <tr>
            <td><b>pep</b></td>
            <td>StrBoolean (optional)ing</td>
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
            <td><b>riskLevel</b></td>
            <td>String (optional)</br><b>Enum:</b></br>
[NONE,LOW,MEDIUM,HIGH,EXTREME]</td>
            <td>EXTREME</td>
            <td>Customer risk level</td>
        </tr>
        <tr>
            <td><b>status</b></td>
            <td>String (optional)</br><b>Enum:</b></br>
[ACTIVE, PENDING, REJECTED, SUSPENDED, CLOSED]</td>
            <td>ACTIVE</td>
            <td>Customer status in Amlyze system</td>
        </tr>
    </tbody>
</table> 

---

> Optional values omitted

```json
{
  "specversion": "1.0",
  "type": "com.amlyze.customer.updated",
  "source": "customer",
  "subject": "customerExtid",
  "id": "1234-1234-1234",
  "time": "2018-04-05T17:31:00Z",
  "datacontenttype": "application/json",
  "data": {
    "sanctioned": true,
    "pep": true,
    "inAdverseMedia":true,
    "riskLevel": "EXTREME",
    "status": "PENDING"
  }
}

{
  "specversion": "1.0",
  "type": "com.amlyze.customer.updated",
  "source": "customer",
  "subject": "customerExtid",
  "id": "1234-1234-1234",
  "time": "2018-04-05T17:31:00Z",
  "datacontenttype": "application/json",
  "data": {
    "sanctioned": true,
    "pep": true,
  }
}

{
  "specversion": "1.0",
  "type": "com.amlyze.customer.updated",
  "source": "customer",
  "subject": "customerExtid",
  "id": "1234-1234-1234",
  "time": "2018-04-05T17:31:00Z",
  "datacontenttype": "application/json",
  "data": {
    "pep": true,
  }
}
```