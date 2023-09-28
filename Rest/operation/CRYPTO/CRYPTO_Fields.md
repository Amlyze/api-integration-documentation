# Operation
In any type of operation between two or more parties, one of the parties is always the customer. The other party(ies) are called counterparties. Every possible operation with its own mandatory and possible fields is provided below.

---

# CRYPTO

<table>
    <thead>
        <tr>
            <td ><b> field </td>
            <td ><b> type </td>
            <td ><b> mandatory </td>
            <td ><b> example </td>
            <td><b> description </td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td ><b> communicationNumber  </td>
            <td > String </td>
            <td ><b> true </td>
            <td > ComNr_0011 </td>
            <td> Unique number of communication  </td>
        </tr>
        <tr>
            <td ><b> requester </td>
            <td > String </td>
            <td > <b> true </td>
            <td > Branch Name </td>
            <td> Name of the system requesting web service </td>
        </tr>
        <tr>
            <td ><b> operationExtId </td>
            <td > String </td>
            <td > <b> true </td>
            <td > Op_22xx22 </td>
            <td> External identifier of operation </td>
        </tr>
        <tr>
            <td ><b> operationType  </td>
            <td > String </td>
            <td > <b> true  </td>
            <td > CRYPTO </td>
            <td> Notifies about what kind of operation was performed </td>
        </tr>
        <tr>
            <td ><b> sourceOfRiskLevel </td>
            <td > <b>ENUM</b> <br/>[EVALUATE,<br/>IMPORT] </td>
            <td > <b> true </td>
            <td > EVALUATE </td>
            <td> Source of risk level<br> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed. </br> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment </td>
        </tr>
         <tr>
            <td ><b> operationDateTime </td>
            <td > Date </td>
            <td > <b> true </td>
            <td > 2023-03-16T13:00:00Z </td>
            <td> The operation date and time show when the operation proceeded with  </td>
        </tr>
        <tr>
            <td ><b> operationStatus </td>
            <td ><b> ENUM</b><br/>[EXECUTED,<br/>REJECTED] </td>
            <td > true/false </td>
            <td > EXECUTED </td>
            <td> Either operation was successfully executed, or the operation was rejected </br> <b> Mandatory</b> when sourceOfRiskLevel = IMPORT </td>
        </tr>
        <tr>
            <td ><b> riskLevel </td>
            <td > ENUM</b><br/>[NONE,<br/>LOW,<br/>NEDIUM,<br/>HIGH,<br/>EXTREME] </td>
            <td > false </td>
            <td > LOW </td>
            <td>The risk level of imported operation</td>
        </tr>
        <tr>
            <td ><b> riskManagementCategory </td>
            <td > String </td>
            <td > <b> true </td>
            <td > OP_PK </td>
            <td> Code of risk management category of object. Risk management category code from classifier can be checked <a href="https://github.com/Amlyze/api-integration-documentation/Rest/README.md#Classifiers">here</a></td>
        </tr>
         <tr>
            <td ><b> financialFlowDirection </td>
            <td > FinancialFlowDirectionApi </td>
            <td > <b> true </td>
            <td > INCOMING </td>
            <td> Refers to the movement of money between entities or accounts</br>  direction = <b>INCOMING</b> your customer = <b>CREDITOR</b> 
            </br>  direction = <b>OUTGOING</b> your customer = <b>DEBTOR</b>
            </td>
        </tr>
        <tr>
            <td ><b> initializeScreeningProcesses </td>
            <td > List<string> </td>
            <td > false </td>
            <td > PEP,</br>ADVERSE_MEDIA,</br> SANCTIONS </td>
            <td> Defines which lists to check during screening process<br/> ScreeningList code from classifier can be checked <a href="https://github.com/Amlyze/api-integration-documentation/Rest/README.md#Classifiers">here</a></td>
        </tr>
        <tr>
            <td ><b> amount </td>
            <td > BigDecimal </td>
            <td > <b>true </td>
            <td > 1499 </td>
            <td> Field for the money amount sent in an operation </td>
        </tr>
        <tr>
            <td ><b> amountInEuro </td>
            <td > BigDecimal </td>
            <td > true/ false </td>
            <td >  1399</td>
            <td> amount of money in euro currency </td>
        </tr>
        <tr>
            <td ><b> currency </td>
            <td > String </td>
            <td > <b> true</td>
            <td > BTC </td>
            <td> Currency code from classifier.</br> Currency code from classifier can be checked <a href="https://github.com/Amlyze/api-integration-documentation/Rest/README.md#Classifiers">here</a></td> 
        </tr>
        <tr>
            <td ><b> description </td>
            <td > String </td>
            <td > <b> true </td>
            <td > "Fund Transfer" </td>
            <td> The purpose of payment is saved under description.<br/> It is necessary for the operation to be proceeded </td>
        </tr>
        <tr>
            <td ><b> sourceCountry </td>
            <td > String </td>
            <td > false </td>
            <td > LT </td>
            <td> Source country informs about where the operation was initiated </td>
        </tr>
        <tr>
            <td ><b> destinationCountry </td>
            <td >String  </td>
            <td > false </td>
            <td > LT </td>
            <td> Country of operation's destination </td>
        </tr>
        <tr>
            <td ><b> euroExchangeRate </td>
            <td > BigDecimal </td>
            <td > true/false </td>
            <td > 0.93 </td>
            <td> Euro exchange rate for other than Euro currency<br/> 
            <b>Mandatory</b> when currency =! <b>eur</b></br> <b>Not Used</b> when currency = <b>eur</b></td>
        </tr>
        <tr>
            <td ><b> ipAddress </td>
            <td > String </td>
            <td > false </td>
            <td > xxx.zzz.yyyy.www </td>
            <td> The IP address of the operation </td>
        </tr>
        <tr>
            <td ><b> ipAddressCountry </td>
            <td > String </td>
            <td > false </td>
            <td > LT </td>
            <td> Country of an IP address of the operation </td>
        </tr>
         <tr>
            <td ><b>[ListOperationParty]</td>
            <td > OperationPartyApi </td>
            <td > <b> true </td>
            <td > - </td>
            <td> List of entities that belong to one operation| </td>
        </tr>
    </tbody>
</table>

## Operation Party

At least one operation party account must exist in Amlyze (identified by accountNumber, BIC, Currency)


<table>
    <thead>
        <tr>
            <td ><b> field </td>
            <td ><b> type </td>
            <td ><b> mandatory </td>
            <td ><b> example </td>
            <td ><b> description </td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td ><b> accountNumber </td>
            <td > String </td>
            <td > <b>true </td>
            <td > 1fe09d5554aaaa22ccccaa </td>
            <td> Unique account identification number used in performing operations </td>
        </tr>
        <tr>
            <td ><b> bankTitle </td>
            <td > String </td>
            <td > false </td>
            <td >TBC bank  </td>
            <td> Title of bank with which the operation is happening </td>
        </tr>
        <tr>
            <td ><b> bic </td>
            <td > String </td>
            <td > true/false </td>
            <td > BICXX22 </td>
            <td> Bank identifier code for account number </br> <b>Mandatory</b> for customer</br> <b>Not Mandatory</b> for counterparty</td>
        </tr>
        <tr>
            <td ><b> entityType </td>
            <td >  <b>ENUM</b><br/>[INDIVIDUAL,<br/>ORGANIZATION,<br/>UNKNOWN] </td>
            <td ><b> true </td>
            <td > INDIVIDUAL </td>
            <td> Describes client status.<br/>  UNKNOWN is valid only for counterparty (not a customer) </td>
        </tr>
        <tr>
            <td ><b> currency </td>
            <td > String </td>
            <td > <b> true/false </td>
            <td > EUR </td>
            <td> Currency code of operation </br> <b>Mandatory</b> for  customer, </br> <b>Not Mandatory</b> for counterparty </td>
        </tr>
        <tr>
            <td ><b> partyRole </td>
            <td >  <b>ENUM</b> <br/>[DEBTOR,<br/>CREDITOR]  </td>
            <td > <b>true </td>
            <td > CREDITOR </td>
            <td> The role of the party in on-going operation </td>
        </tr>
        <tr>
            <td ><b> firstName </td>
            <td > String </td>
            <td > true/false </td>
            <td > Eduardo </td>
            <td> <b>Mandatory</b> when entityType = <b> INDIVIDUAL</b>or <b>UNKNOWN</b> </br> <b>Not Used</b> when entityType = <b>ORGANIZATION</b> </td>
        </tr>
        <tr>
            <td ><b> lastName </td>
            <td > String </td>
            <td > true/false </td>
            <td > Rodriguez </td>
            <td> <b>Mandatory</b> when entityType = <b> INDIVIDUAL</b>or <b>UNKNOWN</b> </br> <b>Not Used</b> when entityType = <b>ORGANIZATION</b> </td>
        </tr>
        <tr>
            <td ><b> title </td>
            <td > String </td>
            <td > true/false </td>
            <td > Moller </td>
            <td> <b>Mandatory</b> when entityType = <b>ORGANIZATION</b>or <b>UNKNOWN</b> </br> <b>Not Mandatory</b> when entityType = <b>INDIVIDUAL</b> </td>
        </tr>
    </tbody>
</table>
