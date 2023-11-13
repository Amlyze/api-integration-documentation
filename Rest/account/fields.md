# Account

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
			<td>ComNr_000321</td>
			<td>Unique number of communication. Used for risk assessment callback</td>
		</tr>
        <tr>
			<td><b>requester</b></td>
			<td>String</td>
			<td>true</td>
			<td>ComNr_000321</td>
			<td>Name of the system requesting web service</td>
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
            <td><b>bankTitle</b></td>
            <td>String</td>
            <td>false</td>
            <td>TBC bank</td>
            <td>Title of bank with which the operation is happening</td>
        </tr>
        <tr>
            <td><b>accountExtId</b></td>
            <td>String</td>
            <td>true</td>
            <td>Acc_0011</td>
            <td>External account identification number used to track activity regarding the specific account</td>
        </tr>
        <tr>
            <td><b>accountNumber</b></td>
            <td>String</td>
            <td>true</td>
            <td>LT705734389447757988</td>
            <td>Unique account identification number used in performing operations</td>
        </tr>
        <tr>
            <td><b>accountPurpose</b></td>
            <td>String</td>
            <td>false</td>
            <td>PURPOSE_INVEST</td>
            <td>The purpose of owning the account in question</td>
        </tr>
        <tr>
            <td><b>accountStatus</b></td>
            <td><b>ENUM</b> <br/> [ACTIVE, <br/>SUSPENDED,<br/> CLOSED]</td>
            <td>true</td>
            <td>ACTIVE</td>
            <td>Refers to the current condition or state of an account</td>
        </tr>
        <tr>
            <td><b>accountType</b></td>
            <td>String</td>
            <td>false</td>
            <td>ORG_B2B</td>
            <td>Categorizes accounts by their intended purposes and features</td>
        </tr>
        <tr>
            <td><b>bic</b></td>
            <td>String</td>
            <td>true</td>
            <td>BICXX22</td>
            <td>Bank identifier code for account number</td>
        </tr>
        <tr>
            <td><b>businessEntityExtId</b></td>
            <td>String</td>
            <td>true</td>
            <td>ExtId_0012</td>
            <td>External business entity indicator. Refers to the same value used for the <br/><b>customerExtId</b>, which helps to identify external business entity</td>
        </tr>
        <tr>
            <td><b>openingDate</b></td>
            <td>Date</td>
            <td>true</td>
            <td>2022-12-10T12:10:11+02:00</td>
            <td>Account opening date</td>
        </tr>
        <tr>
            <td><b>closingDate</b></td>
            <td>Date</td>
            <td>true/false</td>
            <td>2022-12-11T12:10:11+02:00</td>
            <td>Account closing date <br/> <b>Mandatory</b> only when accountStatus = CLOSED</td>
        </tr>
        <tr>
            <td><b>currencyCode</b></td>
            <td>String</td>
            <td>true</td>
            <td>EUR</td>
            <td>International currency code</td>
        </tr>
        <tr>
            <td><b>isOtherFinInstAccount</b></td>
            <td>Boolean</td>
            <td>false</td>
            <td>false</td>
            <td>Declaring whether the account belongs to other financial institution</td>
        </tr>
        <tr>
            <td><b>suspensionReasons</b></td>
            <td>String</td>
            <td>false</td>
            <td>Security breach investigation in progress</td>
            <td>A reason for suspension can be provided only if the account status is SUSPENDED</td>
        </tr>
    </tbody>
</table>
