w# Operation
In any type of operation between two or more parties, one of the parties is always the customer. The other party(ies) are called counterparties. Every possible operation with its own mandatory and possible fields is provided below.

---

# CARD_PAYMENT

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
            <td>financial_institution</td>
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
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Operation type classifier)</a>
            </td>
            <td>true</td>
            <td>CARD_PAYMENT</td>
            <td>Notifies about what kind of operation was performed</td>
        </tr>
        <tr>
            <td><b>cardOperationSubType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Card operation subType classifier)</a>
            </td>
            <td>true</td>
            <td>CARD_PURCHASE</td>
            <td>Card operation subtype code</td>
        </tr>
        <tr>
            <td><b>riskManagementCategory</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Risk management category classifier)</a>
            </td>
            <td>true</td>
            <td>OP_DEFAULT</td>
            <td>Code of risk management category of object.</td>
        </tr>
        <tr>
            <td><b>initializeScreeningProcesses</b></td>
            <td>String[]</td>
            <td>false</td>
            <td>PEP,<br/>ADVERSE_MEDIA,<br/> SANCTIONS</td>
            <td>Defines which lists to check during screening process.</td>
        </tr>
        <tr>
            <td><b>sourceOfRiskLevel</b></td>
            <td>String<br/><b>ENUM</b><br/>[EVALUATE,<br/>IMPORT]</td>
            <td>true</td>
            <td>EVALUATE</td>
            <td>Source of risk level<br/> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed.<br/> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment</td>
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
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Business unit classifier)</a>
            </td>
			<td>true/false</td>
			<td>BUSINESS_UNIT_NAME</td>
			<td>This parameter is mandatory only for clients utilizing a multi-organizational solution. 
            ❗<b>Omit this parameter unless instructed about it.</b>❗</br> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data. Each business unit can have its own set of users, permissions, and data access rules. </br><i>(Upcoming feature)</i></td>
		</tr>
        <tr>
            <td><b>financialFlowDirection</b></td>
            <td>String<br/><b>ENUM</b><br/>[INCOMING,<br/>LOW,<br/>OUTGOING,<br/>NULL]</td>
            <td>true</td>
            <td>INCOMING</td>
            <td>Refers to the movement of money between entities or accounts<br/>  direction = <b>INCOMING</b> your customer = <b>CREDITOR</b> 
           <br/>  direction = <b>OUTGOING</b> your customer = <b>DEBTOR</b>
            </td>
        </tr>
         <tr>
            <td><b>currency</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Currency classifier)</a>
            </td>
            <td>true</td>
            <td>EUR</td>
            <td>Currency code.</td> 
        </tr>
        <tr>
            <td><b>amount</b></td>
            <td>BigDecimal</td>
            <td>true</td>
            <td>1499</td>
            <td>Field for the money amount sent in an operation</td>
        </tr>
        <tr>
            <td><b>amountInEuro</b></td>
            <td>BigDecimal</td>
            <td>true/ false</td>
            <td>1399</td>
            <td>amount of money in euro currency</td>
        </tr>
        <tr>
            <td><b>euroExchangeRate</b></td>
            <td>BigDecimal</td>
            <td>true/false</td>
            <td>0.93</td>
            <td>Euro exchange rate for other than Euro currency<br/> 
            <b>Mandatory</b> when currency =! <b>eur</b><br/> <b>Not Used</b> when currency = <b>eur</b></td>
        </tr>
        <tr>
            <td><b>description</b></td>
            <td>String</td>
            <td>true</td>
            <td>"Fund Transfer"</td>
            <td>The purpose of payment is saved under description.<br/> It is necessary for the operation to be proceeded</td>
        </tr>
        <tr>
            <td><b>sourceCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
            <td>false</td>
            <td>LT</td>
            <td>Source country informs about where the operation was initiated</td>
        </tr>
        <tr>
            <td><b>destinationCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
            <td>false</td>
            <td>LT</td>
            <td>Country of operation's destination</td>
        </tr>
        <tr>
            <td><b>ipAddress</b></td>
            <td>String</td>
            <td>false</td>
            <td>xxx.zzz.yyyy.www</td>
            <td>The IP address of the operation</td>
        </tr>
        <tr>
            <td><b>ipAddressCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
            <td>false</td>
            <td>LT</td>
            <td>Country of an IP address of the operation</td>
        </tr>
        <tr>
            <td><b>merchantCode</b></td>
            <td>String</td>
            <td>false</td>
            <td>5541</td>
            <td>External identifier of the seller-mediator</td>
        </tr>
        <tr>
            <td><b>merchantCountryCode</b></td>
            <td>String</td>
            <td>false</td>
            <td>LT</td>
            <td>Seller-mediator Country code</td>
        </tr>
        <tr>
            <td><b>merchantDescription</b></td>
            <td>String</td>
            <td>false</td>
            <td>"Ecommerce merchants"</td>
            <td>Seller-mediator description</td>
        </tr>
        <tr>
            <td><b>merchantExtId</b></td>
            <td>String</td>
            <td>false</td>
            <td>External_0112</td>
            <td>External identifier of the seller-mediator</td>
        </tr>
        <tr>
            <td><b>merchantName</b></td>
            <td>String</td>
            <td>false</td>
            <td>Costco</td>
            <td>Name of the seller-mediator</td>
        </tr>
         <tr>
            <td><b>salesPointCode</b></td>
            <td>String</td>
            <td>false</td>
            <td>54574</td>
            <td>External code of the sales point</td>
        </tr>
         <tr>
            <td><b>salesPointExtId</b></td>
            <td>String</td>
            <td>false</td>
            <td>S_extid_0145</td>
            <td>External identifier of the sales point</td>
        </tr>
         <tr>
            <td><b>terminalCode</b></td>
            <td>String</td>
            <td>false</td>
            <td>57455</td>
            <td>External code of terminal</td>
        </tr>
         <tr>
            <td><b>terminalExtId</b></td>
            <td>String</td>
            <td>false</td>
            <td>t_extid_145</td>
            <td>External identifier of the terminal</td>
        </tr>
        <tr>
            <td><b>ListOperationParty</b></td>
            <td><a href="#OperationPartyApi">OperationPartyApi[]</a></td>
            <td>true</td>
            <td>-</td>
            <td>List of entities that belong to one operation</td>
        </tr>
    </tbody>
</table>


## OperationPartyApi

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
            <td>CREDITOR</td>
            <td>The role of the party in ongoing operation. </br> When "partyRole", is one of <b>"ULTIMATE_"</b>, only two variations of elements becomes <b>mandatory</b> to provide:</br> 1. "entityType",</br> 2. "identifier" | "firstName" + "lastName" | "title"</td>
        </tr>
        <tr>
            <td><b>accountNumber</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>LT038625979279192518</td>
            <td>Unique account identification number used in performing operations. </br> <b>Mandatory</b> only when <b>"partyRole" = "DEBTOR" | "CREDITOR"</b> </td>
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
            <td>Bank identifier code for account number<br/> <b>Mandatory</b> for customer<br/> <b>Not Mandatory</b> for counterparties</td>
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
            <td>String<br/><b>ENUM</b><br/>[INDIVIDUAL,<br/>ORGANIZATION,<br/>UNKNOWN]</td>
            <td>true</td>
            <td>INDIVIDUAL</td>
            <td>Describes client status.<br/> <b>UNKNOWN</b> is valid only for counterparties</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Eduardo</td>
            <td>Individual's or Unknown entity's first name, <b>used only together with "lastName"</b> and never alone</td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Rodriguez</td>
            <td>Individual's or Unknown entity's last name, <b>used only together with "firstName"</b> and never alone</td>
        </tr>
        <tr>
            <td><b>title</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Moller</td>
		    <td>Identifies a party (individual, organization, or unknown) without requiring "firstName" or "lastName."</td>
        </tr>
        <tr>
            <td><b>identifier</b></td>
			<td>String </td>
            <td>true/false</td>
            <td>50007153359</td>
            <td>Unique identification number (e.g., personal ID, company VAT code) to distinguish the payer and the transaction. </br> Becomes <b>Mandatory</b> only when <b>"partyRole" = "ULTIMATE_"</b> and no more elements are provided for that party </td>
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
         <tr>
            <td><b>cardHolderName</b></td>
            <td>String </td>
            <td>false</td>
            <td>Eduardo Rodrigues</td>
            <td>Data from card</td>
        </tr>
        <tr>
            <td><b>cardNumber</b></td>
            <td>String</td>
            <td>false</td>
            <td>4720582145647937</td>
            <td>Data from card</td>
        </tr>
        <tr>
            <td><b>cardValidTill</b></td>
            <td>String</td>
            <td>false</td>
            <td>2025-06-07</td>
            <td>Data from card</td>
        </tr>
    </tbody>
</table>
       