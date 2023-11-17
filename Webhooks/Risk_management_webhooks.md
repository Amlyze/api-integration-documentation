# Risk management webhooks (callbacks)

## Risk management events Envelope

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>type</b></td>
            <td>String</td>
            <td>"app.amlyze.customer.riskmanagement.kyc_scoring.completed"</td>
            <td>Unique event type. Check documentation below to see available types</td>
        </tr>
        <tr>
            <td><b>specversion</b></td>
            <td>String</td>
            <td>"1.0"</td>
            <td><a href="https://cloudevents.io/"> Cloud Events Specification version that is being used</td>
        </tr>
        <tr>
            <td><b>source</b></td>
             <td>URI-reference</br><b>Enum:</b></br>[customer]</br><a href="https://datatracker.ietf.org/doc/html/rfc3986#section-4.1">FC 3986 - Uniform Resource Identifier (URI): Generic Syntax</a></td> 
            <td>"893af30c-7dda-44b2-bf98-476da6ca4326"</td>
            <td>Event source - request ID (communication number)</td>
        </tr>
        <tr>
            <td><b>subject</b></td>
            <td>String</td>
            <td>"extId"</td>
            <td>Event subject represents a resource external id</td>
        </tr>
        <tr>
            <td><b>id</b></td>
            <td>String</td>
            <td>"0412a5ca-3be7-46b7-87de-38366397602e"</td>
            <td>Unique event ID</td>
        </tr>
        <tr>
            <td><b>time</b></td>
            <td>Timestamp</td>
            <td>"2023-06-16T09:23:21.575405178Z"</td>
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
            <td>Event response. Differs on the event type</td>
        </tr>
    </tbody>
<table>

---

# Customer KYC events

## app.amlyze.customer.riskmanagement.kyc_scoring.pending
> The event is fired when a human decision is needed

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>initialRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The initial risk level is shown based on during evaluation given result</td>
        </tr>
    </tbody>
<table>

* **Example:**
```json
{ "initialRiskLevel": "LOW" }
```

---
## app.amlyze.customer.riskmanagement.kyc_scoring.waiting_for_approval_date
> This event is sent when configuration is set to wait for customer approval date

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>initialRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The initial risk level is shown based on during evaluation given result</td>
        </tr>
        <tr>
            <td><b>finalRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The final risk level</td>
        </tr>
        <tr>
            <td><b>decisionType</b></td>
            <td>String</br><b>Enum</b></br>[ACCEPTED, REJECTED]</td>
            <td>"ACCEPTED"</td>
            <td>Decision type</td>
        </tr>
        <tr>
            <td><b>decisionGroundCode</b></td>
            <td>String <i>(optional)</i></br>
Decision grounds can be checked by reaching <a href="../Rest/README.md/#classifiers">(Decision Ground classifier)</a></td>
            <td>"anystring"</td>
            <td>description which indicates the selected decision for resolving a case.<br/><i>Return only if a human decision were needed</i></td>
        </tr>
    </tbody>
<table>

* **Example:**

```json
{
  "initialRiskLevel": "LOW",
   "finalRiskLevel": "LOW",
   "decisionType": "ACCEPTED",
   "decisionGroundCode": "01"
}
```
---

## app.amlyze.customer.riskmanagement.kyc_scoring.completed
> The event is fired always on completion by a human decision/automatically resolved

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>initialRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The initial risk level is shown based on during evaluation given result</td>
        </tr>
        <tr>
            <td><b>finalRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The final risk level</td>
        </tr>
        <tr>
            <td><b>decisionType</b></td>
            <td>String</br><b>Enum</b></br>[ACCEPTED, REJECTED]</td>
            <td>"ACCEPTED"</td>
            <td>Decision type</td>
        </tr>
        <tr>
            <td><b>decisionGroundCode</b></td>
            <td>String <i>(optional)</i></br>
Decision grounds can be checked by reaching <a href="../Rest/README.md/#classifiers">(Decision Ground classifier)</a></td>
            <td>"anystring"</td>
            <td>description which indicates the selected decision for resolving a case.<br/><i>Return only if a human decision were needed</i></td>
        </tr>
        <tr>
            <td><b>approvedAt</b></td>
            <td>Timestamp <i>(optional)</i></br>RFC 3339 (ISO 8601)</td>
            <td>"2018-04-05T17:31:00Z"</td>
            <td>Approval date.</br><i>Set first time in the system</i></td>
        </tr>
    </tbody>
<table>


* **Example:**

```json
{
  "initialRiskLevel": "LOW",
   "finalRiskLevel": "LOW",
   "decisionType": "ACCEPTED",
   "decisionGroundCode": "01",
   "approvedAt": "2018-04-05T17:31:00Z"
}
```
---

# Lead KYC Scroring Events

## app.amlyze.lead.riskmanagement.kyc_scoring.pending
> The event is fired when a human decision is needed

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>initialRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The initial risk level is shown based on during evaluation given result</td>
        </tr>
    </tbody>
<table>

* **Example:**

```json
{ "initialRiskLevel": "LOW" }
```

---

## app.amlyze.lead.riskmanagement.kyc_scoring.completed
> The event is fired always on completion by a human decision/automatically resolved

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>initialRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The initial risk level is shown based on during evaluation given result</td>
        </tr>
        <tr>
            <td><b>finalRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The final risk level.</td>
        </tr>
        <tr>
            <td><b>decisionType</b></td>
            <td>String</br><b>Enum</b></br>[ACCEPTED, REJECTED]</td>
            <td>"ACCEPTED"</td>
            <td>Decision type</td>
        </tr>
        <tr>
            <td><b>decisionGroundCode</b></td>
            <td>String <i>(optional)</i></br>
Decision grounds can be checked by reaching <a href="../Rest/README.md/#classifiers">(Decision Ground classifier)</a></td>
            <td>"anystring"</td>
            <td>Every decision ground code has its own description which indicates the selected decision for resolving a case.<br><i>Return only if a human decision were needed</i></td>
        </tr>
    </tbody>
<table>


* **Example:**

```json
{
  "initialRiskLevel": "LOW",
   "finalRiskLevel": "LOW",
   "decisionType": "ACCEPTED",
   "decisionGroundCode": "01",
}
```

---

# Operation Real-time Monitoring events

## app.amlyze.operation.riskmanagement.operation_realtime.pending
> The event is fired when a human decision is needed

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>initialRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The initial risk level is shown based on during evaluation given result</td>
        </tr>
    </tbody>
<table>

* **Example:**

```json
{ "initialRiskLevel": "LOW" }
```

---
## app.amlyze.operation.riskmanagement.operation_realtime.completed
> The event is fired always on completion by a human decision/automatically resolved

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Exemplary JSON Value</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>initialRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The initial risk level is shown based on during evaluation given result</td>
        </tr>
        <tr>
            <td><b>finalRiskLevel</b></td>
            <td>String</br><b>Enum</b></br>[NONE, LOW, MEDIUM, HIGH, EXTREME]</td>
            <td>"LOW"</td>
            <td>The final risk level</td>
        </tr>
        <tr>
            <td><b>decisionType</b></td>
            <td> <td>String</br><b>Enum</b></br>[ACCEPTED, REJECTED]</td></td>
            <td>"ACCEPTED"</td>
            <td>Decision type</td>
        </tr>
        <tr>
            <td><b>decisionGroundCode</b></td>
            <td>String <i>(optional)</i></br>
Decision grounds can be checked by reaching <a href="../Rest/README.md/#classifiers">(Decision Ground classifier)</a></td>
            <td>"anystring"</td>
            <td>Every decision ground code has its own description which indicates the selected decision for resolving a case.<br><i>Return only if a human decision were needed</i></td>
        </tr>
    </tbody>
<table>

* **Example:**
  
```json
{
    "initialRiskLevel": "LOW",
    "finalRiskLevel": "LOW",
    "decisionType": "ACCEPTED",
    "decisionGroundCode": "01"
 }
```
