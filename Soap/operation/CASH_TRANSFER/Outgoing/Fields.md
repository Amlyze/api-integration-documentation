# Cash Transfer Outgoing

# API Endpoint

* **URL Structure:**  `http://[host][port][path][service]`

* **Example:** `http://{{host}}:8878/amlyze-ws/EvaluateOperationV2Service`

---
# Additional info

* **METHOD:** `POST`
* **Auth required:** `NO`
* **Content-Type:** `text/xml`

---
# Conditions

* Both `OperationParty` sides covers the same entity
* * `DEBTOR` is the sender
* `CREDITOR` is the receiver
* "Transfer of funds by cash payment"
  
# Workflow

* Creating a new operation→ <SourceOfRiskLevel>EVALUATE</SourceOfRiskLevel>
* An operation that took place in the past → <SourceOfRiskLevel>IMPORT</SourceOfRiskLevel>
* If during EVALUATE, case was generated → Human decision is required
  
---

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Mandatory</b></td>
            <td><b>Example</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>CommunicationNumber</b></td>
            <td>String</td>
            <td>true</td>
            <td>ComNr_0011</td>
            <td>Unique number of communication. This field can store up to 256 characters</td>
        </tr>
        <tr>
            <td><b>            <td><b>Requester</b></td>
</b></td>
            <td>String</td>
            <td>true</td>
            <td>Kauno kredito unija</td>
            <td>Name of the system requesting web service</td>
        </tr>
         <tr>
            <td><b>RiskManagementCategory</b></td>
            <td>String <br/>
                <a href="../../../../Classifiers/classifiers.md">(Risk management category classifier)</a></td>
            <td>true</td>
            <td>OP_DEFAULT</td>
            <td>Code of risk management category of object</a></td>
        </tr>
        <tr>
			<td><b>BusinessUnit</b></td>
			<td>
                String <br/>
                <a href="../../../../Classifiers/classifiers.md">(Business unit classifier)</a>
            </td>
			<td>true/false</td>
			<td>BUSINESS_UNIT_NAME</td>
			<td>This parameter is mandatory only for clients utilizing a multi-organizational solution. 
            ❗<b>Omit this parameter unless instructed about it.</b>❗<br/> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data. Each business unit can have its own set of users, permissions, and data access rules. <br/><i>(Upcoming feature)</i></td>
		</tr>
        <tr>
            <td><b>SourceOfRiskLevel</b></td>
            <td>String<br/><b>ENUM</b><br/>[EVALUATE,<br/>IMPORT]</td>
            <td>true</td>
            <td>IMPORT</td>
            <td>Source of risk level<br/> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed.<br/> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment</td>
        </tr>
        <tr>
            <td><b>OperationStatus</b></td>
            <td>String<br/><b>ENUM</b><br/>[EXECUTED,<br/>REJECTED]</td>
            <td>true/false</td>
            <td>EXECUTED</td>
            <td>Either operation was successfully executed, or the operation was rejected<br/> <b> Mandatory</b> when sourceOfRiskLevel = IMPORT</td>
        </tr>
        <tr>
            <td><b>OperationType</b></td>
            <td>String</td>
            <td>true</td>
            <td>CASH_TRANSFER</td>
            <td>Notifies about what kind of operation was performed</td>
        </tr>
        <tr>
            <td><b>FinancialFlowDirection</b></td>
            <td>FinancialFlowDirectionApi</td>
            <td>true</td>
            <td>OUTGOING</td>
            <td>Refers to the movement of money between entities or accounts</td>
        </tr>
        <tr>
            <td><b>operationExtId</b></td>
            <td>String</td>
            <td>true</td>
            <td>OP20231114T12</td>
            <td>External identifier of operation</td>
        </tr>
        <tr>
            <td><b>OperationDateTime</b></td>
            <td>Date</td>
            <td>true</td>
            <td>2023-03-16T13:00:00Z</td>
            <td>The operation date and time show when the operation proceeded with</td>
        </tr>
        <tr>
            <td><b>Amount</b></td>
            <td>BigDecimal</td>
            <td>true</td>
            <td>1435</td>
            <td>Field for the money amount sent in an operation</td>
        </tr>
        <tr>
            <td><b>Currency</b></td>
            <td>String <br/>
                <a href="../../../../Classifiers/classifiers.md">(Currency classifier)</a></td>
            <td>true</td>
            <td>GBP</td>
            <td>Currency code from classifier</td> 
        </tr>
        <tr>
            <td><b>AmountInEuro</b></td>
            <td>BigDecimal</td>
            <td>true/ false</td>
            <td>1640.06</td>
            <td>amount of money in euro currency.<br/><b>Mandatory</b> when currency =! <b>eur</b><br/> <b>Not Used</b> when currency = <b>eur</b></td>
        </tr>
        <tr>
            <td><b>EuroExchangeRate</b></td>
            <td>BigDecimal</td>
            <td>true/false</td>
            <td>1.14</td>
            <td>Euro exchange rate for other than Euro currency<br/> 
            <b>Mandatory</b> when currency =! <b>eur</b><br/> <b>Not Used</b> when currency = <b>eur</b></td>
        <tr>
            <td><b>Description</b></td>
            <td>String</td>
            <td>true</td>
            <td>"Transfer of funds by cash payment"</td>
            <td>The purpose of payment is saved under description.<br/> It is necessary for the operation to be proceeded</td>
        </tr>
        <tr>
            <td><b>RiskLevel</b></td>
            <td>String<br/><b>ENUM</b><br/>[NONE,<br/>LOW,<br/>MEDIUM,<br/>HIGH,<br/>EXTREME]</td>
            <td>false</td>
            <td>LOW</td>
            <td>The risk level of imported operation</td>
        </tr>
        <tr>
            <td><b>initializeScreeningProcesses</b></td>
            <td>String[]</td>
            <td>false</td>
            <td>PEP,<br/>ADVERSE_MEDIA,<br/> SANCTIONS</td>
            <td>Defines which lists to check during screening process.</td>
        </tr>
        <tr>
            <td><b>SourceCountry</b></td>
            <td>String <br/>
                <a href="../../../../Classifiers/classifiers.md">(Country classifier)</a></td>
            <td>false</td>
            <td>LT</td>
            <td>Source country informs about where the operation was initiated</td>
        </tr>
        <tr>
            <td><b>DestinationCountry</b></td>
            <td>String</td>
            <td>false</td>
            <td>LT</td>
            <td>Country of operation's destination</td>
        </tr>
        </tr>
        <tr>
            <td><b>ListOperationParty</b></td>
            <td><a href="#OperationPartyApi">[OperationPartyApi]</a></td>
            <td>true</td>
            <td>-</td>
            <td>List of entities that belong to one operation|</td>
        </tr>
    </tbody>
</table>


## OperationPartyAPI

At least one operation party account must exist in Amlyze (identified by accountNumber, BIC, Currency)


<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Mandatory</b></td>
            <td><b>Example</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
    <tr>
            <td><b>PartyRole</b></td>
            <td>String<br/><b>ENUM</b><br/>[DEBTOR,<br/>CREDITOR]</td>
            <td>true</td>
            <td>DEBTOR</td>
            <td>The role of the party in ongoing operation</td>
        </tr>
        <tr>
            <td><b>AccountNumber</b></td>
            <td>String</td>
            <td>true</td>
            <td>LT038625979279192518</td>
            <td>Unique account identification number used in performing operations</td>
        </tr>
        <tr>
            <td><b>BIC</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>BICXX22</td>
            <td>Bank identifier code for the account number<br/><b>Mandatory</b> for CREDITOR only</td>
        </tr>
        <tr>
            <td><b>Currency</b></td>
            <td>String</td>
            <td>false</td>
            <td>GBP</td>
            <td>Currency tag can be not provided - in that case, it is derived from the above-inserted operation's Currency code</td>
        </tr>
        <tr>
            <td><b>BankTitle</b></td>
            <td>String</td>
            <td>false</td>
            <td>TBC bank</td>
            <td>Title of bank to which the cash goes to</td>
        </tr>
         <tr>
            <td><b>EntityType</b></td>
            <td>String<br/><b>ENUM</b><br/>[INDIVIDUAL,<br/>ORGANIZATION]</td>
            <td>true</td>
            <td>INDIVIDUAL</td>
            <td>Describes client status</td>
        </tr>
        <tr>
            <td><b>FirstName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Geli</td>
            <td><b>Mandatory</b> when entityType = INDIVIDUAL<br/><b>Not Used</b> when entityType = ORGANIZATION</td>
        </tr>
        <tr>
            <td><b>LastName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Deliono</td>
            <td><b>Mandatory</b> when entityType = INDIVIDUAL<br/><b>Not Used</b> when entityType = ORGANIZATION</td>
        </tr>
        <tr>
            <td><b>Title</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>UAB 'Brotherhood'</td>
            <td><b>Mandatory</b> when entityType = ORGANIZATION<br/><b>Not Mandatory</b> when entityType = INDIVIDUAL</td>
        </tr>
    </tbody>
</table>
