# Operation

<table>
    <thead>
        <tr>
            <td style="text-align:center"><b> field </td>
            <td style="text-align:center"><b> type </td>
            <td style="text-align:center"><b> mandatory </td>
            <td style="text-align:center"><b> example </td>
            <td style="text-align:center"><b> description </td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:center"><b> communicationNumber  </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"><b> true </td>
            <td style="text-align:center"> ComNr_0011 </td>
            <td> Unique number of communication  </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> requester </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> Branch Name </td>
            <td> Name of the system requesting web service </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> operationExtId </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> Op_22xx22 </td>
            <td> External identifier of operation </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> operationType  </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b> true  </td>
            <td style="text-align:center"> SEPA </td>
            <td> Notifies about what kind of operation was performed </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> sourceOfRiskLevel </td>
            <td style="text-align:center"> <b>ENUM</b> <br/>[EVALUATE,<br/>IMPORT] </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> EVALUATE </td>
            <td> Source of risk level<br> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed. </br> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> amount </td>
            <td style="text-align:center"> BigDecimal </td>
            <td style="text-align:center"> <b>true </td>
            <td style="text-align:center"> 1499 </td>
            <td> Field for the money amount sent in an operation </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> amountInEuro </td>
            <td style="text-align:center"> BigDecimal </td>
            <td style="text-align:center"> true/ false </td>
            <td style="text-align:center">  1399</td>
            <td> amount of money in euro currency </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> cardOperationSubType </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> true/false </td>
            <td style="text-align:center"> CARD_PURCHASE </td>
            <td> <b>Mandatory</b> when operationType = CARD_PAYMENT or CARD_CASH <br/>   CardOperationSubType code from classifier can be checked <a href="https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers">here</a></td>
        </tr>
        <tr>
            <td style="text-align:center"><b> currency </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b> true</td>
            <td style="text-align:center"> EUR </td>
            <td> Currency code from classifier:*</br> Currency code from classifier can be checked <a href="https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers">here</a></td> 
        </tr>
        <tr>
            <td style="text-align:center"><b> dateAuthorized </td>
            <td style="text-align:center"> Date </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> 2023-05-10T12:10:11+02:00 </td>
            <td> Date and Time of operation </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> dateSettled </td>
            <td style="text-align:center"> Date </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> 2023-05-101T15:10:11+02:00 </td>
            <td> Date and Time of operation </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> description </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> "Fund Transfer" </td>
            <td> The purpose of payment is saved under description.<br/> It is necessary for the operation to be proceeded </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> sourceCountry </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> LT </td>
            <td> Source country informs about where the operation was initiated </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> destinationCountry </td>
            <td style="text-align:center">String  </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> LT </td>
            <td> Country of operation's destination </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> euroExchangeRate </td>
            <td style="text-align:center"> BigDecimal </td>
            <td style="text-align:center"> true/false </td>
            <td style="text-align:center"> 0.93 </td>
            <td> Euro exchange rate for other than Euro currency<br/> 
            <b>Mandatory</b> when currency =! <b>eur</b></br> <b>Not Used</b> when currency = <b>eur</b></td>
        </tr>
        <tr>
            <td style="text-align:center"><b> fastPayment </td>
            <td style="text-align:center"> Boolean </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> <b> true </td>
            <td> Identification if payment should be processed immediately<br/> <i>Default value is false </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> financialFlowDirection </td>
            <td style="text-align:center"> FinancialFlowDirectionApi </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> INCOMING </td>
            <td> Refers to the movement of money between entities or accounts  </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> initializeScreeningProcesses </td>
            <td style="text-align:center"> List<string> </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> PEP,</br>ADVERSE_MEDIA,</br> SANCTIONS </td>
            <td> Defines which lists to check during screening process<br/> ScreeningList code from classifier can be checked <a href="https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers">here</a></td>
        </tr>
        <tr>
            <td style="text-align:center"><b> ipAddress </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> xxx.zzz.yyyy.www </td>
            <td> The IP address of the operation </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> ipAddressCountry </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> LT </td>
            <td> Country of an IP address of the operation </td>
        </tr>
        <tr>
            <td style="text-align:center"><b><a href="#operation-party">[ListOperationParty]</a> </td>
            <td style="text-align:center"> OperationPartyApi </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> - </td>
            <td> List of entities that belong to one operation| </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> merchantCode </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> 5541 </td>
            <td> External identifier of the seller-mediator </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> merchantCountryCode </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> LT </td>
            <td> Seller-mediator Country code </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> merchantDescription </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> "Ecommerce merchants" </td>
            <td> Seller-mediator description </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> merchantExtId </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> External_0112 </td>
            <td> External identifier of the seller-mediator </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> merchantName </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> Costco </td>
            <td> Name of the seller-mediator </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> operationDateTime </td>
            <td style="text-align:center"> Date </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> 2023-03-16T13:00:00Z </td>
            <td> The operation date and time show when the operation proceeded with  </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> operationStatus </td>
            <td style="text-align:center"><b> ENUM</b><br/>[EXECUTED,<br/>REJECTED] </td>
            <td style="text-align:center"> true/false </td>
            <td style="text-align:center"> EXECUTED </td>
            <td> Either operation was successfully executed, or the operation was rejected </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> riskLevel </td>
            <td style="text-align:center"> ENUM</b><br/>[NONE,<br/>LOW,<br/>NEDIUM,<br/>HIGH,<br/>EXTREME] </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> LOW </td>
            <td>The risk level of imported operation <br/> 
            <b>Mandatory</b> when sourceOfRiskLEvel = <b>IMPORT</b></br> <b>Not Used</b> when sourceOfRiskLEvel = <b>EVALUATE</b> </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> riskManagementCategory </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> OP_PK </td>
            <td> Code of risk management category of object. Risk management category code from classifier can be checked <a href="https://github.com/Amlyze/api-integration-documentation/blob/main/README.md#Classifiers">here</a></td>
        </tr>
         <tr>
            <td style="text-align:center"><b> salesPointCode </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> 54574 </td>
            <td> External code of the sales point </td>
        </tr>
         <tr>
            <td style="text-align:center"><b> salesPointExtId </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> S_extid_0145 </td>
            <td> External identifier of the sales point </td>
        </tr>
         <tr>
            <td style="text-align:center"><b> terminalCode </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> 57455 </td>
            <td> External code of terminal </td>
        </tr>
         <tr>
            <td style="text-align:center"><b> terminalExtId </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> t_extid_145 </td>
            <td> External identifier of the terminal </td>
        </tr>
    </tbody>
</table>


# Operation Party

At least one operation party account must exist in Amlyze (identified by accountNumber, BIC, Currency)


<table>
    <thead>
        <tr>
            <td style="text-align:center"><b> field </td>
            <td style="text-align:center"><b> type </td>
            <td style="text-align:center"><b> mandatory </td>
            <td style="text-align:center"><b> example </td>
            <td style="text-align:center"><b> description </td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td style="text-align:center"><b> accountNumber </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b>true </td>
            <td style="text-align:center"> LT038625979279192518 </td>
            <td> Unique account identification number used in performing operations </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> bankTitle </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center">TBC bank  </td>
            <td> Title of bank with which the operation is happening </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> bic </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"><b> true </td>
            <td style="text-align:center"> BICXX22 </td>
            <td> Bank identifier code for account number </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> entityType </td>
            <td style="text-align:center">  <b>ENUM</b><br/>[INDIVIDUAL,<br/>ORGANIZATION,<br/>UNKNOWN] </td>
            <td style="text-align:center"><b> true </td>
            <td style="text-align:center"> INDIVIDUAL </td>
            <td> Describes client status.<br/>  UNKNOWN is valid only for counterparty (not a customer) </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> currency </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> GBP </td>
            <td> Currency code of operation </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> partyRole </td>
            <td style="text-align:center">  <b>ENUM</b> <br/>[DEBTOR,<br/>CREDITOR,<br/>ULTIMATE_DEBTOR,<br/>ULTIMATE_CREDITOR]  </td>
            <td style="text-align:center"> <b>true </td>
            <td style="text-align:center"> CREDITOR </td>
            <td> The role of the party in on-going operation </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> firstName </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> true/false </td>
            <td style="text-align:center"> Eduardo </td>
            <td> <b>Mandatory</b> when entityType = <b> INDIVIDUAL</b>or <b>UNKNOWN</b> </br> <b>Not Used</b> when entityType = <b>ORGANIZATION</b> </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> lastName </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> true/false </td>
            <td style="text-align:center"> Rodriguez </td>
            <td> <b>Mandatory</b> when entityType = <b> INDIVIDUAL</b>or <b>UNKNOWN</b> </br> <b>Not Used</b> when entityType = <b>ORGANIZATION</b> </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> title </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> true/false </td>
            <td style="text-align:center"> Moller </td>
            <td> <b>Mandatory</b> when entityType = <b>ORGANIZATION</b>or <b>UNKNOWN</b> </br> <b>Not Mandatory</b> when entityType = <b>INDIVIDUAL</b> </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> cardHolderName </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> Eduardo Rodrigues </td>
            <td> Data from card </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> cardNumber </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> 4720582145647937 </td>
            <td> Data from card </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> cardValidTill </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> 2025-06-07 </td>
            <td> Data from card </td>
        </tr>
    </tbody>
</table>