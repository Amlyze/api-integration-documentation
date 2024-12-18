# Cash outgoing operation

**Samples**

* [evaluateMandatory.json](CASH/outgoing/samples/evaluateMandatory.json)
* [evaluateFull.json](CASH/outgoing/samples/evaluateFull.json)
* [importMandatory.json](CASH/outgoing/samples/importMandatory.json)
* [importFull.json](CASH/outgoing/samples/importFull.json)

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
            <td><b>communicationNumber</b></td>
            <td>String</td>
            <td>true</td>
            <td>ComNr_0011</td>
            <td>Unique number of communication. This field can store up to 256 characters</td>
        </tr>
        <tr>
            <td><b>requester</b></td>
            <td>String</td>
            <td>true</td>
            <td>Kauno kredito unija</td>
            <td>Name of the system requesting web service</td>
        </tr>
    	<tr>
            <td><b>operationExtId</b></td>
            <td>String</td>
            <td>true</td>
            <td>Op_22xx22</td>
            <td>External identifier of operation</td>
        </tr>	
        <tr>
            <td><b>operationType</b></td>
            <td>String <br/>
                <a href="https://github.com/Amlyze/api-integration-documentation/blob/main/Classifiers/classifiers.md">(Operation type classifier)</a>
            </td>
            <td>true</td>
            <td>CASH</td>
            <td>Notifies about what kind of operation was performed</td>
        </tr>
         <tr>
            <td><b>riskManagementCategory</b></td>
            <td>String <br/>
                <a href="../../../../Classifiers/classifiers.md">(Risk management category classifier)</a></td>
            <td>true</td>
            <td>OP_DEFAULT</td>
            <td>Code of risk management category of object</a></td>
        </tr>
        <tr>
            <td><b>initializeScreeningProcesses</b></td>
            <td>String[]</td>
            <td>false</td>
            <td>PEP,<br/>ADVERSE_MEDIA,<br/> SANCTIONS, <br/>INTERNAL_LIST</td>
            <td><div>🚨<b>Alert:</b> Field omitted in batch request.</div>Defines which lists to check during screening process</td>
        </tr>
	<tr>
            <td><b>sourceOfRiskLevel</b></td>
            <td>String<br/><b>ENUM</b><br/>[EVALUATE,<br/>IMPORT]</td>
            <td>true</td>
            <td>EVALUATE</td>
            <td><div>🚨<b>Alert:</b> Field omitted in batch request and by default is <b>IMPORT</b>.</div> Source of risk level<br/> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed.<br/> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment</td>
        </tr>
	<tr>
            <td><b>operationDateTime</b></td>
            <td>Date</td>
            <td>true</td>
            <td>2023-03-16T13:00:00Z</td>
            <td>The operation date and time show when the operation proceeded with</td>
        </tr>
	<tr>
            <td><b>operationStatus</b></td>
            <td>String<br/><b>ENUM</b><br/>[EXECUTED,<br/>REJECTED]</td>
            <td>true/false</td>
            <td>EXECUTED</td>
            <td>Either operation was successfully executed, or the operation was rejected<br/> <b> Mandatory</b> when sourceOfRiskLevel = IMPORT</td>
        </tr>
	<tr>
            <td><b>riskLevel</b></td>
            <td>String<br/><b>ENUM</b><br/>[NONE,<br/>LOW,<br/>MEDIUM,<br/>HIGH,<br/>EXTREME]</td>
            <td>false</td>
            <td>LOW</td>
            <td>The risk level of imported operation</td>
        </tr>
	<tr>
	    <td><b>businessUnit</b></td>
	    <td>String <br/>
                <a href="../../../Classifiers/classifiers.md">(Business unit classifier)</a>
            </td>
	    <td>true/false</td>
	    <td>BUSINESS_UNIT_NAME</td>
	    <td>This parameter is mandatory only for clients utilizing a multi-organizational solution. 
            ❗<b>Omit this parameter unless instructed about it.</b>❗<br/> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data. Each business unit can have its own set of users, permissions, and data access rules. <br/><i>(Upcoming feature)</i></td>
	</tr>
        <tr>
            <td><b>financialFlowDirection</b></td>
            <td>String<br/><b>ENUM</b><br/>[INCOMING,<br/><b>OUTGOING</b>]</td>
            <td>true</td>
            <td>OUTGOING</td>
            <td>Refers to the movement of money between entities or accounts</td>
        </tr>
        <tr>
            <td><b>currency</b></td>
            <td>String <br/>
                <a href="../../../../Classifiers/classifiers.md">(Currency classifier)</a></td>
            <td>true</td>
            <td>GBP</td>
            <td>Currency code from classifier</td> 
        </tr>
	<tr>
            <td><b>amount</b></td>
            <td>BigDecimal</td>
            <td>true</td>
            <td>1435</td>
            <td>Field for the money amount sent in an operation</td>
        </tr>
        <tr>
            <td><b>amountInEuro</b></td>
            <td>BigDecimal</td>
            <td>true/ false</td>
            <td>1640.06</td>
            <td>amount of money in euro currency.<br/><b>Mandatory</b> when currency =! <b>eur</b><br/> <b>Not Used</b> when currency = <b>eur</b></td>
        </tr>
        <tr>
            <td><b>euroExchangeRate</b></td>
            <td>BigDecimal</td>
            <td>true/false</td>
            <td>1.14</td>
            <td>Euro exchange rate for other than Euro currency<br/> 
            <b>Mandatory</b> when currency =! <b>eur</b><br/> <b>Not Used</b> when currency = <b>eur</b></td>
        <tr>
            <td><b>description</b></td>
            <td>String</td>
            <td>true</td>
            <td>"Cash withdrawal"</td>
            <td>The purpose of payment is saved under description.<br/> It is necessary for the operation to be proceeded</td>
        </tr>
        <tr>
            <td><b>sourceCountry</b></td>
            <td>String <br/>
                <a href="../../../../Classifiers/classifiers.md">(Country classifier)</a></td>
            <td>false</td>
            <td>LT</td>
            <td>Source country informs about where the operation was initiated</td>
        </tr>
        <tr>
            <td><b>destinationCountry</b></td>
            <td>String <br/>
                <a href="../../../../Classifiers/classifiers.md">(Country classifier)</a></td>
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
            <td><b>partyRole</b></td>
            <td>String<br/><b>ENUM</b><br/>[DEBTOR,<br/>CREDITOR,<br/>ULTIMATE_DEBTOR,<br/>ULTIMATE_CREDITOR]</td>
            <td>true</td>
            <td>DEBTOR</td>
            <td>The role of the party in ongoing operation. <br/> When "partyRole", is one of <b>"ULTIMATE_"</b>, only two variations of elements becomes <b>mandatory</b> to provide:<br/> 1. "entityType",<br/> 2. "identifier" | "firstName" + "lastName" | "title"</td>
        </tr>
        <tr>
            <td><b>accountNumber</b></td>
            <td>String</td>
            <td>true</td>
            <td>LT038625979279192518</td>
            <td>IBAN or any unique identification number generated during account creation. If unique identification number was not created - customer's "customerExtId" (used during customer creation ) can be used. <br/> when direction "OUTGOING" Debtor's account number = customer account & Creditor's account number =  unique identification number/customer's externalId</td>
        </tr>
        <tr>
            <td><b>currency</b></td>
            <td>String <br/><a href="../../../Classifiers/classifiers.md">(Currency classifier)</a></td>
            <td>false</td>
            <td>GBP</td>
            <td>Currency code of operation</td>
        </tr>
	<tr>
            <td><b>bic</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>BICXX22</td>
            <td>Bank identifier code for the account number<br/><b>Mandatory</b> for DEBTOR only</td>
        </tr>
        <tr>
            <td><b>bankTitle</b></td>
            <td>String</td>
            <td>false</td>
            <td>TBC bank</td>
            <td>Title of bank with which the operation is happening</td>
        </tr>
         <tr>
            <td><b>entityType</b></td>
            <td>String<br/><b>ENUM</b><br/>[INDIVIDUAL,<br/>ORGANIZATION]</td>
            <td>true</td>
            <td>INDIVIDUAL</td>
            <td>Describes client status</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Eduardo</td>
            <td>Individual entity's first name, <b>used only together with "lastName"</b> and never alone</td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Rodriguez</td>
            <td>Individual entity's last name, <b>used only together with "firstName"</b> and never alone</td>
        </tr>
        <tr>
            <td><b>title</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Moller</td>
	    <td>Identifies a party (individual, organization) without requiring "firstName" or "lastName."</td>
        </tr>
        <tr>
            <td><b>identifier</b></td>
	    <td>String </td>
            <td>true/false</td>
            <td>50007153359</td>
            <td>Unique identification number (e.g., personal ID, company VAT code) to distinguish the payer and the transaction. <br/> Becomes <b>Mandatory</b> only when <b>"partyRole" = "ULTIMATE_"</b> and no more elements are provided for that party </td>
        </tr>
        <tr>
            <td><b>address</b></td>
	    <td>String </td>
            <td>false</td>
            <td>Verkių g. 7-8, Vilnius</td>
            <td>Contact information including street address, city, and possibly other relevant details</td>
        </tr>
        <tr>
            <td><b>country</b></td>
	    <td>String <br/><a href="../../../Classifiers/classifiers.md">(Country classifier)</a></td>
            <td>false</td>
            <td>LT</td>
            <td>Two-letter country code (e.g., US, DE) specifying the participant's country</td>
        </tr>
    </tbody>
</table>
