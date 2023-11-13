# Operation
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
            <td>Unique number of communication</td>
        </tr>
        <tr>
            <td><b>requester</b></td>
            <td>String</td>
            <td>true</td>
            <td>Branch Name</td>
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
            <td>String</td>
            <td>true</td>
            <td>CARD_PAYMENT</td>
            <td>Notifies about what kind of operation was performed</td>
        </tr>
        <tr>
            <td><b>sourceOfRiskLevel</b></td>
            <td><b>ENUM</b> <br/>[EVALUATE,<br/>IMPORT]</td>
            <td>true</td>
            <td>EVALUATE</td>
            <td>Source of risk level<br> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed.<br/> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment</td>
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
            <td><b>ENUM</b><br/>[EXECUTED,<br/>REJECTED]</td>
            <td>true/false</td>
            <td>EXECUTED</td>
            <td>Either operation was successfully executed, or the operation was rejected<br/> <b> Mandatory</b> when sourceOfRiskLevel = IMPORT</td></td>
        </tr>
        <tr>
            <td><b>riskLevel</b></td>
            <td>ENUM<b></b><br/>[NONE,<br/>LOW,<br/>NEDIUM,<br/>HIGH,<br/>EXTREME]</td>
            <td>false</td>
            <td>LOW</td>
            <td>The risk level of imported operation</td>
        </tr>
        <tr>
            <td><b>riskManagementCategory</b></td>
            <td>String</td>
            <td>true</td>
            <td>OP_DEFAULT</td>
            <td>Code of risk management category of object. Risk management category code from classifier can be checked <a href="../../README.md#classifiers">here</a></td>
        </tr>
		<tr>
			<td><b>businessUnit</b></td>
			<td>String <br/>(classifier)</td>
			<td>true/false</td>
			<td>BUSINESS_UNIT_NAME</td>
			<td>
                Unit data identification for controllability/observability.
                <br/>❗NOTE: parameter is required only if business unit strict mode enabled
            </td>
		</tr>
        <tr>
            <td><b>financialFlowDirection</b></td>
            <td>FinancialFlowDirectionApi</td>
            <td>true</td>
            <td>INCOMING</td>
            <td>Refers to the movement of money between entities or accounts<br/>  direction = <b>INCOMING</b> your customer = <b>CREDITOR</b> 
           <br/>  direction = <b>OUTGOING</b> your customer = <b>DEBTOR</b>
        </td>
        </tr>
        <tr>
            <td><b>cardOperationSubType</b></td>
            <td>String</td>
            <td>true</td>
            <td>CARD_PURCHASE</td>
            <td>CardOperationSubType code from classifier can be checked <a href="../../README.md#classifiers">here</a></td>
        </tr>
        <tr>
            <td><b>initializeScreeningProcesses</b></td>
            <td>String[]</td>
            <td>false</td>
            <td>PEP,<br/>ADVERSE_MEDIA,<br/> SANCTIONS</td>
            <td>Defines which lists to check during screening process<br/> ScreeningList code from classifier can be checked <a href="../../README.md#classifiers">here</a></td>
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
            <td><b>currency</b></td>
            <td>String</td>
            <td>true</td>
            <td>EUR</td>
            <td>Currency code from classifier.<br/> Currency code from classifier can be checked <a href="../../README.md#classifiers">here</a></td> 
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
            <td>String</td>
            <td>false</td>
            <td>LT</td>
            <td>Source country informs about where the operation was initiated</td>
        </tr>
        <tr>
            <td><b>destinationCountry</b></td>
            <td>String</td>
            <td>false</td>
            <td>LT</td>
            <td>Country of operation's destination</td>
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
            <td><b>ipAddress</b></td>
            <td>String</td>
            <td>false</td>
            <td>xxx.zzz.yyyy.www</td>
            <td>The IP address of the operation</td>
        </tr>
        <tr>
            <td><b>ipAddressCountry</b></td>
            <td>String</td>
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
            <td><b>[ListOperationParty]</b></td>
            <td>OperationPartyApi</td>
            <td>true</td>
            <td>-</td>
            <td>List of entities that belong to one operation|</td>
        </tr>
    </tbody>
</table>


## Operation Party

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
            <td><b>accountNumber</b></td>
            <td>String</td>
            <td>true</td>
            <td>LT038625979279192518</td>
            <td>Unique account identification number used in performing operations</td>
        </tr>
        <tr>
            <td><b>bankTitle</b></td>
            <td>String</td>
            <td>false</td>
            <td>TBC bank</td>
            <td>Title of bank with which the operation is happening</td>
        </tr>
        <tr>
            <td><b>bic</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>BICXX22</td>
            <td>Bank identifier code for account number<br/> <b>Mandatory</b> for customer<br/> <b>Not Mandatory</b> for counterparty</td>
        </tr>
        <tr>
            <td><b>entityType</b></td>
            <td><b>ENUM</b><br/>[INDIVIDUAL,<br/>ORGANIZATION,<br/>UNKNOWN]</td>
            <td>true</td>
            <td>INDIVIDUAL</td>
            <td>Describes client status.<br/>  UNKNOWN is valid only for counterparty (not a customer)</td>
        </tr>
        <tr>
            <td><b>currency</b></td>
            <td>String</td>
            <td>false</td>
            <td>EUR</td>
            <td>Currency code of operation</td>
        </tr>
        <tr>
            <td><b>partyRole</b></td>
            <td><b>ENUM</b> <br/>[DEBTOR,<br/>CREDITOR]</td>
            <td>true</td>
            <td>CREDITOR</td>
            <td>The role of the party in ongoing operation</td>
        </tr>
        <tr>
            <td><b>firstName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Eduardo</td>
            <td><b>Mandatory</b> when entityType = <b> INDIVIDUAL</b>or <b>UNKNOWN</b><br/> <b>Not Used</b> when entityType = <b>ORGANIZATION</b></td>
        </tr>
        <tr>
            <td><b>lastName</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Rodriguez</td>
            <td><b>Mandatory</b> when entityType = <b> INDIVIDUAL</b>or <b>UNKNOWN</b><br/> <b>Not Used</b> when entityType = <b>ORGANIZATION</b></td>
        </tr>
        <tr>
            <td><b>title</b></td>
            <td>String</td>
            <td>true/false</td>
            <td>Moller</td>
            <td><b>Mandatory</b> when entityType = <b>ORGANIZATION</b>or <b>UNKNOWN</b><br/> <b>Not Mandatory</b> when entityType = <b>INDIVIDUAL</b></td>
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
