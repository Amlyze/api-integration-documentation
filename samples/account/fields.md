# Account
​
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
			<td style="text-align:center"><b> communicationNumber </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> ComNr_000321 </td>
			<td> Unique number of communication. Used for risk assessment callback </td>
		</tr>
        <tr>
			<td style="text-align:center"><b> requester  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> ComNr_000321 </td>
			<td> Name of the system requesting web service </td>
		</tr>
        <tr>
            <td style="text-align:center"><b> bankTitle </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center">TBC bank  </td>
            <td> Title of bank with which the operation is happening </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> accountExtId </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> <b>true </td>
            <td style="text-align:center"> Acc_0011  </td>
            <td> External account identification number used to track activity regarding the specific account </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> accountNumber </td>
            <td style="text-align:center">String </td>
            <td style="text-align:center"> <b>true </td>
            <td style="text-align:center">LT705734389447757988  </td>
            <td> Unique account identification number used in performing operations</td>
        </tr>
        <tr>
            <td style="text-align:center"><b> accountPurpose </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center">PURPOSE_INVEST  </td>
            <td> The purpose of owning the account in question </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> accountStatus </td>
            <td style="text-align:center"> <b>ENUM</b> <br/> [ACTIVE, <br/>SUSPENDED,<br/> CLOSED] </td>
            <td style="text-align:center"><b> true </td>
            <td style="text-align:center">ACTIVE  </td>
            <td> Refers to the current condition or state of an account </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> accountType </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center">ORG_B2B  </td>
            <td> Categorizes accounts by their intended purposes and features </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> bic </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"><b> true </td>
            <td style="text-align:center"> BICXX22 </td>
            <td> Bank identifier code for account number </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> businessEntityExtId </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"><b> true </td>
            <td style="text-align:center"> ExtId_0012 </td>
            <td> External business entity indicator. Refers to the same value used for the <br/<b>customerExtId</b>, which helps to identify external business entity </td>
        </tr>
        <tr>
            <td style="text-align:center"><b>openingDate  </td>
            <td style="text-align:center"> Date </td>
            <td style="text-align:center"> <b> true </td>
            <td style="text-align:center"> 2022-12-10T12:10:11+02:00 </td>
            <td> Account opening date  </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> closingDate </td>
            <td style="text-align:center">Date  </td>
            <td style="text-align:center"> true/false </td>
            <td style="text-align:center"> 2022-12-11T12:10:11+02:00 </td>
            <td> Account closing date </br> <b>Mandatory</b> only when accountStatus = CLOSED </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> currencyCode </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center"><b> true </td>
            <td style="text-align:center"> EUR </td>
            <td> International currency code </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> isOtherFinInstAccount </td>
            <td style="text-align:center"> Boolean </td>
            <td style="text-align:center"> false </td>
            <td style="text-align:center"> false </td>
            <td> Declaring whether the account belongs to other financial institution </td>
        </tr>
        <tr>
            <td style="text-align:center"><b> suspensionReasons </td>
            <td style="text-align:center"> String </td>
            <td style="text-align:center">false  </td>
            <td style="text-align:center"> Security breach investigation in progress </td>
            <td> A reason for suspension can be provided only if the account status is SUSPENDED </td>
        </tr>
    </tbody>
  </table>  


