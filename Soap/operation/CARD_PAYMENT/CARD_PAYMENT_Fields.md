# Operation
In any type of operation between two or more parties, one of the parties is always the customer. The other party(ies) are called counterparties. Every possible operation with its own mandatory and possible fields is provided below.

---
## CARD_PAYMENT conditions
* CARD_PAYMENT operations can have up to two <b>"OperationParty" </b> members, where one of them will always be your customer
* During `OUTGOING` financial flow operation→ your Customer 's <b>"PartyRole"</b> can be:
    * DEBTOR
* During `INCOMING` financial flow operation→ your Customer 's <b>"PartyRole"</b> can be:
    * CREDITOR
* Field <b>"Action"</b> with value `UPDATE` → is not possible for operations
* Field <b>"CardOperationSubType" </b> becomes Mandatory for CARD operations

## CARD_PAYMENT WorkFlow
* Creating a new operation → value for a field <b>"SourceOfRiskLevel"</b> is `EVALUATE`
* An operation that took place in the past → value for a field <b>"SourceOfRiskLevel"</b> is `IMPORT`
* If during `EVALUATE`, case was generated → Human decision is required
---

# CARD_PAYMENT

<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Mandatory</b></td>
            <td><b>Example/Ref</b></td>
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
            <td><b>Requester</b></td>
            <td>String</td>
            <td>true</td>
            <td>financial_institution</td>
            <td>Name of the system requesting web service</td>
        </tr>
        <tr>
            <td><b>OperationExtId</b></td>
            <td>String</td>
            <td>true</td>
            <td>Op_22xx22</td>
            <td>External identifier of operation</td>
        </tr>
        <tr>
            <td><b>OperationType</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Operation type classifier)</a>
            </td>
            <td>true</td>
            <td>CARD_CASH</td>
            <td>Notifies about what kind of operation was performed</td>
        </tr>
        <tr>
            <td><b>SourceOfRiskLevel</b></td>
            <td>String<br/><b>ENUM</b><br/>[EVALUATE,<br/>IMPORT]</td>
            <td>true</td>
            <td>EVALUATE</td>
            <td>Source of risk level<br/> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed.<br/> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment</td>
        </tr>
        <tr>
            <td><b>OperationDateTime</b></td>
            <td>Date</td>
            <td>true</td>
            <td>2023-03-16T13:00:00Z</td>
            <td>The operation date and time show when the operation proceeded with</td>
        </tr>
        <tr>
            <td><b>OperationStatus</b></td>
            <td>String<br/><b>ENUM</b><br/>[EXECUTED,<br/>REJECTED]</td>
            <td>true/false</td>
            <td>EXECUTED</td>
            <td>Either operation was successfully executed, or the operation was rejected<br/> <b> Mandatory</b> when sourceOfRiskLevel = IMPORT</td>
        </tr>
        <tr>
            <td><b>RiskLevel</b></td>
            <td>String<br/><b>ENUM</b><br/>[NONE,<br/>LOW,<br/>MEDIUM,<br/>HIGH,<br/>EXTREME]</td>
            <td>false</td>
            <td>LOW</td>
            <td>The risk level of imported operation</td>
        </tr>
        <tr>
            <td><b>RiskManagementCategory</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Risk management category classifier)</a>
            </td>
            <td>true</td>
            <td>OP_DEFAULT</td>
            <td>Code of risk management category of object.</td>
        </tr>
		<tr>
			<td><b>BusinessUnit</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Business unit classifier)</a>
            </td>
			<td>true/false</td>
			<td>BUSINESS_UNIT_NAME</td>
			<td>This parameter is mandatory only for clients utilizing a multi-organizational solution. 
            ❗<b>Omit this parameter unless instructed about it.</b>❗<br/> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data. Each business unit can have its own set of users, permissions, and data access rules. <br/><i>(Upcoming feature)</i></td>
		</tr>
        <tr>
            <td><b>FinancialFlowDirection</b></td>
            <td>String<br/><b>ENUM</b><br/>[INCOMING,<br/>LOW,<br/>OUTGOING,<br/>NULL]</td>
            <td>true</td>
            <td>INCOMING</td>
            <td>
                Refers to the movement of money between entities or accounts<br/>  direction = <b>INCOMING</b> your customer = <b>CREDITOR</b> 
                <br/>  direction = <b>OUTGOING</b> your customer = <b>DEBTOR</b>
            </td>
        </tr>
		<tr>
			<td><b>InitializeScreeningProcesses</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#Process">Process[]</a></td>
			<td>Defines which lists to check during screening process.</td>
		</tr>
        <tr>
            <td><b>cardOperationSubType</b></td>
			<td>String </td>
            <td>true</td>
            <td>CARD_PURCHASE</td>
            <td>Card operation subtype code (generated during onboarding process). <br/> Common examples: <br/> [CARD_PURCHASE,<br/> CARD_CASH_WITHDRAWAL,<br/> CARD_ACCOUNT_FUNDING_TRANSACTION,<br/> CARD_PAYMENT_CREDIT <br/> CARD_REFUND] </td>
        </tr>
        <tr>
            <td><b>Amount</b></td>
            <td>BigDecimal</td>
            <td>true</td>
            <td>1499</td>
            <td>Field for the money amount sent in an operation</td>
        </tr>
        <tr>
            <td><b>AmountInEuro</b></td>
            <td>BigDecimal</td>
            <td>true/ false</td>
            <td>1399</td>
            <td>amount of money in euro currency</td>
        </tr>
        <tr>
            <td><b>Currency</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Currency classifier)</a>
            </td>
            <td>true</td>
            <td>EUR</td>
            <td>Currency code.</td> 
        </tr>
        <tr>
            <td><b>Description</b></td>
            <td>String</td>
            <td>true</td>
            <td>"Fund Transfer"</td>
            <td>The purpose of payment is saved under description.<br/> It is necessary for the operation to be proceeded</td>
        </tr>
        <tr>
            <td><b>SourceCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
            <td>false</td>
            <td>LT</td>
            <td>Source country informs about where the operation was initiated</td>
        </tr>
        <tr>
            <td><b>DestinationCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
            <td>false</td>
            <td>LT</td>
            <td>Country of operation's destination</td>
        </tr>
        <tr>
            <td><b>EuroExchangeRate</b></td>
            <td>BigDecimal</td>
            <td>true/false</td>
            <td>0.93</td>
            <td>Euro exchange rate for other than Euro currency<br/> 
            <b>Mandatory</b> when currency =! <b>eur</b><br/> <b>Not Used</b> when currency = <b>eur</b></td>
        </tr>
        <tr>
            <td><b>IPAddress</b></td>
            <td>String</td>
            <td>false</td>
            <td>xxx.zzz.yyyy.www</td>
            <td>The IP address of the operation</td>
        </tr>
        <tr>
            <td><b>IPAddressCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
            <td>false</td>
            <td>LT</td>
            <td>Country of an IP address of the operation</td>
        </tr>
        <tr>
            <td><b>MerchantCode</b></td>
            <td>String</td>
            <td>false</td>
            <td>5541</td>
            <td>External identifier of the seller-mediator</td>
        </tr>
        <tr>
            <td><b>MerchantCountryCode</b></td>
            <td>String</td>
            <td>false</td>
            <td>LT</td>
            <td>Seller-mediator Country code</td>
        </tr>
        <tr>
            <td><b>MerchantDescription</b></td>
            <td>String</td>
            <td>false</td>
            <td>"Ecommerce merchants"</td>
            <td>Seller-mediator description</td>
        </tr>
        <tr>
            <td><b>MerchantExtId</b></td>
            <td>String</td>
            <td>false</td>
            <td>External_0112</td>
            <td>External identifier of the seller-mediator</td>
        </tr>
        <tr>
            <td><b>MerchantName</b></td>
            <td>String</td>
            <td>false</td>
            <td>Costco</td>
            <td>Name of the seller-mediator</td>
        </tr>
         <tr>
            <td><b>SalesPointCode</b></td>
            <td>String</td>
            <td>false</td>
            <td>54574</td>
            <td>External code of the sales point</td>
        </tr>
         <tr>
            <td><b>SalesPointExtId</b></td>
            <td>String</td>
            <td>false</td>
            <td>S_extid_0145</td>
            <td>External identifier of the sales point</td>
        </tr>
         <tr>
            <td><b>TerminalCode</b></td>
            <td>String</td>
            <td>false</td>
            <td>57455</td>
            <td>External code of terminal</td>
        </tr>
         <tr>
            <td><b>TerminalExtId</b></td>
            <td>String</td>
            <td>false</td>
            <td>t_extid_145</td>
            <td>External identifier of the terminal</td>
        </tr>
        <tr>
            <td><b>ListOperationParty</b></td>
            <td>Object</td>
            <td>true</td>
            <td><a href="#OperationParty">OperationParty[]</a></td>
            <td>List of entities that belong to one operation</td>
        </tr>
    </tbody>
</table>

## Process

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
			<td><b>Example/Ref</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>Process</b></td>
            <td>String</td>
            <td>true</td>
			<td>SANCTIONS,<br/>PEP,<br/> ADVERSE_MEDIA,<br/> INTERNAL_LIST</td>
		</tr>
	</tbody>
</table>

## OperationParty

At least one operation party account must exist in Amlyze (identified by accountNumber, BIC, Currency)


<table>
    <thead>
        <tr>
            <td><b>Field</b></td>
            <td><b>Type</b></td>
            <td><b>Mandatory</b></td>
            <td><b>Example/Ref</b></td>
            <td><b>Description</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>AccountNumber</b></td>
            <td>String</td>
            <td>true</td>
            <td>LT038625979279192518</td>
            <td>Unique account identification number used in performing operations</td>
        </tr>
        <tr>
            <td><b>BankTitle</b></td>
            <td>String</td>
            <td>false</td>
            <td>TBC bank</td>
            <td>Title of bank with which the operation is happening</td>
        </tr>
        <tr>
            <td><b>BIC</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>BICXX22</td>
            <td>Bank identifier code for account number<br/> <b>Mandatory</b> for customer<br/> <b>Not Mandatory</b> for counterparty</td>
        </tr>
        <tr>
            <td><b>EntityType</b></td>
            <td>String<br/><b>ENUM</b><br/>[INDIVIDUAL,<br/>ORGANIZATION,<br/>UNKNOWN]</td>
            <td>true</td>
            <td>INDIVIDUAL</td>
            <td>Describes client status.<br/>  UNKNOWN is valid only for counterparty (not a customer)</td>
        </tr>
        <tr>
            <td><b>Currency</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Currency classifier)</a>
            </td>
            <td>false</td>
            <td>EUR</td>
            <td>Currency code of operation</td>
        </tr>
        <tr>
            <td><b>PartyRole</b></td>
            <td>String<br/><b>ENUM</b><br/>[DEBTOR,<br/>CREDITOR]</td>
            <td>true</td>
            <td>CREDITOR</td>
            <td>The role of the party in ongoing operation</td>
        </tr>
        <tr>
            <td><b>FirstName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Eduardo</td>
            <td><b>Mandatory</b> when entityType = <b> INDIVIDUAL</b>or <b>UNKNOWN</b><br/> <b>Not Used</b> when entityType = <b>ORGANIZATION</b></td>
        </tr>
        <tr>
            <td><b>LastName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Rodriguez</td>
            <td><b>Mandatory</b> when entityType = <b> INDIVIDUAL</b>or <b>UNKNOWN</b><br/> <b>Not Used</b> when entityType = <b>ORGANIZATION</b></td>
        </tr>
        <tr>
            <td><b>Title</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Moller</td>
            <td><b>Mandatory</b> when entityType = <b>ORGANIZATION</b>or <b>UNKNOWN</b><br/> <b>Not Mandatory</b> when entityType = <b>INDIVIDUAL</b></td>
        </tr>
        <tr>
            <td><b>CardHolderName</b></td>
            <td>String</td>
            <td>false</td>
            <td>Eduardo Rodrigues</td>
            <td>Data from card</td>
        </tr>
        <tr>
            <td><b>CardNumber</b></td>
            <td>String</td>
            <td>false</td>
            <td>4720582145647937</td>
            <td>Data from card</td>
        </tr>
        <tr>
            <td><b>CardValidTill</b></td>
            <td>String</td>
            <td>false</td>
            <td>2025-06-07</td>
            <td>Data from card</td>
        </tr>
    </tbody>
</table>

