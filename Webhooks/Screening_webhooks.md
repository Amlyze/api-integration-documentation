# Screening webhooks (Callbacks)

# Envelope

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
             <td>URI-reference</br><a href="https://datatracker.ietf.org/doc/html/rfc3986#section-4.1">FC 3986 - Uniform Resource Identifier (URI): Generic Syntax</a></td> 
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

# Customer Sanctions Screening

## app.amlyze.customer.screening.sanctions.pending
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
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Customer external id</td>
        </tr>
    </tbody>
<table>


## app.amlyze.customer.screening.sanctions.completed
> The event is always fired on screening finished with resolution


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
            <td><b>sanctioned</b></td>
            <td>Boolean <i>(optional)</i></td>
            <td>true</td>
            <td>Customer sanctioned or not. </br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Customer external id</td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>
    </tbody>
<table>

* **Examples:**

```json
{ "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": false }
```
```json
{ "sanctioned": true, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
---
# Customer politically exposed person screening

## app.amlyze.customer.screening.pep.pending
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
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Customer external id</td>
        </tr>
    </tbody>
<table>

## app.amlyze.customer.screening.pep.completed
> The event is always fired on screening finished with resolution

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
            <td><b>pep</b></td>
            <td>Boolean <i>(optional)</i></td>
            <td>true</td>
            <td>The customer is or is not a politically exposed person status. </br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Customer external id</td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>
    </tbody>
<table>

* **Examples:**

```json
{ "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": false }
```
```json
{ "pep": false, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
```json
{ "pep": true, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
---
# Customer adverse media screening

## app.amlyze.customer.screening.adverse_media.pending
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
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Customer external id</td>
        </tr>
    </tbody>
<table>

## app.amlyze.customer.screening.adverse_media.completed
> The event is always fired on screening finished with resolution

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
            <td><b>inAdverseMedia</b></td>
            <td>Boolean <i>(optional)</i></td>
            <td>true</td>
            <td>Customer found in adverse media or not.</br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Customer external id</td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>
    </tbody>
<table>

* **Examples:**

```json
{ "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": false }
```
```json
{ "inAdverseMedia": false, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
```json
{ "inAdverseMedia": true, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```

---
---

# Lead sanctions screening
## app.amlyze.lead.screening.sanctions.pending
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
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Lead external id</td>
        </tr>
    </tbody>
<table>

## app.amlyze.lead.screening.sanctions.completed
> The event is always fired on screening finished with resolution

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
            <td><b>sanctioned</b></td>
            <td>Boolean <i>(optional)</i></td>
            <td>true</td>
            <td>Lead sanctioned or not.</br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Lead external id</td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>
    </tbody>
<table>

* **Examples:**

```json
{ "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": false }
```
```json
{ "sanctioned": false, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
```json
{ "sanctioned": true, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
---
# Lead politically exposed person screening
## app.amlyze.lead.screening.pep.pending
>The event is fired when a human decision is needed

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
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Lead external id</td>
        </tr>
    </tbody>
<table>

## app.amlyze.lead.screening.pep.completed
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
            <td><b>pep</b></td>
            <td>Boolean <i>(optional)</i></td>
            <td>true</td>
            <td>The lead is or is not a politically exposed person status.</br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Lead external id</td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>
    </tbody>
<table>

* **Examples:**

```json
{ "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": false }
```
```json
{ "pep": false, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
```json
{ "pep": true, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
---


# Lead adverse media screening
## app.amlyze.lead.screening.adverse_media.pending
> The event is always fired on screening finished with resolution

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
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Lead external id</td>
        </tr>
    </tbody>
<table>

## app.amlyze.lead.screening.adverse_media.completed
> The event is always fired on screening finished with resolution

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
            <td><b>inAdverseMedia</b></td>
            <td>Boolean <i>(optional)</i></td>
            <td>true</td>
            <td>Lead is found in adverse media or not.</br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>Lead external id</td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>
    </tbody>
<table>

* **Examples:**

```json
{ "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": false }
```
```json
{ "inAdverseMedia": false, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
```json
{ "inAdverseMedia": true, "externalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3", "screeningMatch": true }
```
---
---
# Related entity sanctions screening
## app.amlyze.related_entity.screening.sanctions.pending
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
            <td><b>customerExternalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>External id of customer, to which related entity is related</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String (optional)</td>
            <td>6854a8c1-66c4-4484-916f-9517b1426a52</td>
            <td>Related entity external id</td>
        </tr>
        <tr>
            <td><b>birthDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>1981-08-06</td>
            <td>Related entity birth date</td>
        </tr>
        <tr>
            <td><b>establishmentDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>2021-08-06</td>
            <td>Related entity establishment date</td>
        </tr>
        <tr>
            <td><b>type</b></td>
            <td>String (optional)</br><b>Enum:</b></br>[INDIVIDUAL, ORGANIZATION]</br>YYYY-MM-DD</td>
            <td>INDIVIDUAL</td>
            <td>Related entity type</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String (optional)</td>
            <td>John</td>
            <td>Related entity first name</td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String (optional)</td>
            <td>Doe</td>
            <td>Related entity last name</td>
        </tr>
        <tr>
            <td><b>title</b></td>
            <td>String (optional)</td>
            <td>John Doe</td>
            <td>Related entity title</td>
        </tr>
        <tr>
            <td><b>nationalCode</b></td>
            <td>String (optional)</td>
            <td>32108068863</td>
            <td>Related entity national code</td>
        </tr>
        <tr>
            <td><b>relationCode</b></td>
            <td>String (optional)</td>
            <td>DIRECTOR</td>
            <td><a href="../Rest/README.md/#classifiers">(Relation Type Classifier)</a></td>
        </tr>
        <tr>
            <td><b>countryCode</b></td>
            <td>String (optional)</br>Format: ISO-3166 alpha-2</td>
            <td>LT</td>
            <td>For Individual related entity:</br><i>Citizenship country</i></br>For Organization related entity:</br><i>Registration country</i></br><a href="../Rest/README.md/#classifiers">(Countries Classifier)</a></td>
        </tr>
    </tbody>
<table>

## app.amlyze.related_entity.screening.sanctions.completed
> The event is always fired on screening finished with resolution
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
            <td><b>sanctioned</b></td>
            <td>Boolean (optional)</td>
            <td>true</td>
            <td>Related entity sanctioned or not.</br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>customerExternalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>External id of customer, to which related entity is related</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String (optional)</td>
            <td>6854a8c1-66c4-4484-916f-9517b1426a52</td>
            <td>Related entity external id</td>
        </tr>
        <tr>
            <td><b>birthDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>1981-08-06</td>
            <td>Related entity birth date</td>
        </tr>
        <tr>
            <td><b>establishmentDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>2021-08-06</td>
            <td>Related entity establishment date</td>
        </tr>
        <tr>
            <td><b>type</b></td>
            <td>String (optional)</br><b>Enum:</b></br>[INDIVIDUAL, ORGANIZATION]</br>YYYY-MM-DD</td>
            <td>INDIVIDUAL</td>
            <td>Related entity type</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String (optional)</td>
            <td>John</td>
            <td>Related entity first name</td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String (optional)</td>
            <td>Doe</td>
            <td>Related entity last name</td>
        </tr> 
        <tr>
            <td><b>title</b></td>
            <td>String (optional)</td>
            <td>John Doe</td>
            <td>Related entity title</td>
        </tr>
        <tr>
            <td><b>nationalCode</b></td>
            <td>String (optional)</td>
            <td>32108068863</td>
            <td>Related entity national code</td>
        </tr>
        <tr>
            <td><b>relationCode</b></td>
            <td>String (optional)</td>
            <td>DIRECTOR</td>
            <td><a href="../Rest/README.md/#classifiers">(Relation Type Classifier)</a></td>
        </tr>
        <tr>
            <td><b>countryCode</b></td>
            <td>String (optional)</br>Format: ISO-3166 alpha-2</td>
            <td>LT</td>
            <td>For Individual related entity:</br><i>Citizenship country</i></br>For Organization related entity:</br><i>Registration country</i></br><a href="../Rest/README.md/#classifiers">(Countries Classifier)</a></td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>        
    </tbody>
<table>

* **Examples:**

```json
{
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": false
}
```
```json
{
  "sanctioned": false,
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": true
}
```
```json
{
  "sanctioned": true,
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": true
}
```

---
# Related entity politically exposed person screening
## app.amlyze.related_entity.screening.pep.pending
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
            <td><b>customerExternalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>External id of customer, to which related entity is related</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String (optional)</td>
            <td>6854a8c1-66c4-4484-916f-9517b1426a52</td>
            <td>Related entity external id</td>
        </tr>
        <tr>
            <td><b>birthDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>1981-08-06</td>
            <td>Related entity birth date</td>
        </tr>
        <tr>
            <td><b>establishmentDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>2021-08-06</td>
            <td>Related entity establishment date</td>
        </tr>
        <tr>
            <td><b>type</b></td>
            <td>String (optional)</br><b>Enum:</b></br>[INDIVIDUAL, ORGANIZATION]</br>YYYY-MM-DD</td>
            <td>INDIVIDUAL</td>
            <td>Related entity type</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String (optional)</td>
            <td>John</td>
            <td>Related entity first name</td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String (optional)</td>
            <td>Doe</td>
            <td>Related entity last name</td>
        </tr>
        <tr>
            <td><b>title</b></td>
            <td>String (optional)</td>
            <td>John Doe</td>
            <td>Related entity title</td>
        </tr>
        <tr>
            <td><b>nationalCode</b></td>
            <td>String (optional)</td>
            <td>32108068863</td>
            <td>Related entity national code</td>
        </tr>
        <tr>
            <td><b>relationCode</b></td>
            <td>String (optional)</td>
            <td>DIRECTOR</td>
            <td><a href="../Rest/README.md/#classifiers">(Relation Type Classifier)</a></td>
        </tr>
        <tr>
            <td><b>countryCode</b></td>
            <td>String (optional)</br>Format: ISO-3166 alpha-2</td>
            <td>LT</td>
            <td>For Individual related entity:</br><i>Citizenship country</i></br>For Organization related entity:</br><i>Registration country</i></br><a href="../Rest/README.md/#classifiers">(Countries Classifier)</a></td>
        </tr>
    </tbody>
<table>

## app.amlyze.related_entity.screening.pep.completed
> The event is always fired on screening finished with resolution

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
            <td><b>pep</b></td>
            <td>Boolean (optional)</td>
            <td>true</td>
            <td>Related entity pep or not.</br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>customerExternalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>External id of customer, to which related entity is related</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String (optional)</td>
            <td>6854a8c1-66c4-4484-916f-9517b1426a52</td>
            <td>Related entity external id</td>
        </tr>
        <tr>
            <td><b>birthDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>1981-08-06</td>
            <td>Related entity birth date</td>
        </tr>
        <tr>
            <td><b>establishmentDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>2021-08-06</td>
            <td>Related entity establishment date</td>
        </tr>
        <tr>
            <td><b>type</b></td>
            <td>String (optional)</br><b>Enum:</b></br>[INDIVIDUAL, ORGANIZATION]</br>YYYY-MM-DD</td>
            <td>INDIVIDUAL</td>
            <td>Related entity type</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String (optional)</td>
            <td>John</td>
            <td>Related entity first name</td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String (optional)</td>
            <td>Doe</td>
            <td>Related entity last name</td>
        </tr> 
        <tr>
            <td><b>title</b></td>
            <td>String (optional)</td>
            <td>John Doe</td>
            <td>Related entity title</td>
        </tr>
        <tr>
            <td><b>nationalCode</b></td>
            <td>String (optional)</td>
            <td>32108068863</td>
            <td>Related entity national code</td>
        </tr>
        <tr>
            <td><b>relationCode</b></td>
            <td>String (optional)</td>
            <td>DIRECTOR</td>
            <td><a href="../Rest/README.md/#classifiers">(Relation Type Classifier)</a></td>
        </tr>
        <tr>
            <td><b>countryCode</b></td>
            <td>String (optional)</br>Format: ISO-3166 alpha-2</td>
            <td>LT</td>
            <td>For Individual related entity:</br><i>Citizenship country</i></br>For Organization related entity:</br><i>Registration country</i></br><a href="../Rest/README.md/#classifiers">(Countries Classifier)</a></td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>        
    </tbody>
<table>

* **Examples:**

```json
{
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": false
}
```
```json
{
  "pep": false,
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": true
}
```
```json
{
  "pep": true,
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": true
}


```
---
# Related entity adverse media screening
## app.amlyze.related_entity.screening.adverse_media.pending
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
            <td><b>customerExternalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>External id of customer, to which related entity is related</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String (optional)</td>
            <td>6854a8c1-66c4-4484-916f-9517b1426a52</td>
            <td>Related entity external id</td>
        </tr>
        <tr>
            <td><b>birthDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>1981-08-06</td>
            <td>Related entity birth date</td>
        </tr>
        <tr>
            <td><b>establishmentDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>2021-08-06</td>
            <td>Related entity establishment date</td>
        </tr>
        <tr>
            <td><b>type</b></td>
            <td>String (optional)</br><b>Enum:</b></br>[INDIVIDUAL, ORGANIZATION]</br>YYYY-MM-DD</td>
            <td>INDIVIDUAL</td>
            <td>Related entity type</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String (optional)</td>
            <td>John</td>
            <td>Related entity first name</td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String (optional)</td>
            <td>Doe</td>
            <td>Related entity last name</td>
        </tr>
        <tr>
            <td><b>title</b></td>
            <td>String (optional)</td>
            <td>John Doe</td>
            <td>Related entity title</td>
        </tr>
        <tr>
            <td><b>nationalCode</b></td>
            <td>String (optional)</td>
            <td>32108068863</td>
            <td>Related entity national code</td>
        </tr>
        <tr>
            <td><b>relationCode</b></td>
            <td>String (optional)</td>
            <td>DIRECTOR</td>
            <td><a href="../Rest/README.md/#classifiers">(Relation Type Classifier)</a></td>
        </tr>
        <tr>
            <td><b>countryCode</b></td>
            <td>String (optional)</br>Format: ISO-3166 alpha-2</td>
            <td>LT</td>
            <td>For Individual related entity:</br><i>Citizenship country</i></br>For Organization related entity:</br><i>Registration country</i></br><a href="../Rest/README.md/#classifiers">(Countries Classifier)</a></td>
        </tr>
    </tbody>
<table>

## app.amlyze.related_entity.screening.adverse_media.completed
> The event is always fired on screening finished with resolution

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
            <td><b>inAdverseMedia</b></td>
            <td>Boolean (optional)</td>
            <td>true</td>
            <td>Related entity in adverse media or not.</br> When a screening match is not found then this value is empty because there is no decision.</td>
        </tr>
        <tr>
            <td><b>customerExternalId</b></td>
            <td>String</td>
            <td>bb2274b1-6804-41f3-9e6f-81b9eb6700e3</td>
            <td>External id of customer, to which related entity is related</td>
        </tr>
        <tr>
            <td><b>externalId</b></td>
            <td>String (optional)</td>
            <td>6854a8c1-66c4-4484-916f-9517b1426a52</td>
            <td>Related entity external id</td>
        </tr>
        <tr>
            <td><b>birthDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>1981-08-06</td>
            <td>Related entity birth date</td>
        </tr>
        <tr>
            <td><b>establishmentDate</b></td>
            <td>String (optional)</br>Format: ISO 8601</br>YYYY-MM-DD</td>
            <td>2021-08-06</td>
            <td>Related entity establishment date</td>
        </tr>
        <tr>
            <td><b>type</b></td>
            <td>String (optional)</br><b>Enum:</b></br>[INDIVIDUAL, ORGANIZATION]</br>YYYY-MM-DD</td>
            <td>INDIVIDUAL</td>
            <td>Related entity type</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String (optional)</td>
            <td>John</td>
            <td>Related entity first name</td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String (optional)</td>
            <td>Doe</td>
            <td>Related entity last name</td>
        </tr> 
        <tr>
            <td><b>title</b></td>
            <td>String (optional)</td>
            <td>John Doe</td>
            <td>Related entity title</td>
        </tr>
        <tr>
            <td><b>nationalCode</b></td>
            <td>String (optional)</td>
            <td>32108068863</td>
            <td>Related entity national code</td>
        </tr>
        <tr>
            <td><b>relationCode</b></td>
            <td>String (optional)</td>
            <td>DIRECTOR</td>
            <td><a href="../Rest/README.md/#classifiers">(Relation Type Classifier)</a></td>
        </tr>
        <tr>
            <td><b>countryCode</b></td>
            <td>String (optional)</br>Format: ISO-3166 alpha-2</td>
            <td>LT</td>
            <td>For Individual related entity:</br><i>Citizenship country</i></br>For Organization related entity:</br><i>Registration country</i></br><a href="../Rest/README.md/#classifiers">(Countries Classifier)</a></td>
        </tr>
        <tr>
            <td><b>screeningMatch</b></td>
            <td>Boolean</td>
            <td>true</td>
            <td>An indication that the screening process found any matches</td>
        </tr>        
    </tbody>
<table>


* **Examples:**

```json
{
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": false
}
```

```json
{
  "inAdverseMedia": false,
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": true
}
```

```json
{
  "inAdverseMedia": true,
  "customerExternalId": "bb2274b1-6804-41f3-9e6f-81b9eb6700e3",
  "type": "INDIVIDUAL",
  "firstName": "John",
  "lastName": "Doe",
  "title": "John Doe",
  "nationalCode": "32108068863",
  "relationCode": "OWNER",
  "countryCode": "LT",
  "screeningMatch": true
}

```