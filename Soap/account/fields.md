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
			<td><b>CommunicationNumber</b></td>
			<td>String</td>
			<td>true</td>
			<td>ComNr_000321</td>
			<td>Unique number of communication. Used for risk assessment callback. This field can store up to 256 characters</td>
		</tr>
        <tr>
			<td><b>Requester</b></td>
			<td>String</td>
			<td>true</td>
			<td>financial_institution</td>
			<td>Name of the system requesting web service</td>
		</tr>
		<tr>
			<td><b>BusinessUnit</b></td>
			<td>
                String <br/>
                <a href="../../Classifiers/classifiers.md">(Business unit classifier)</a>
            </td>
			<td>true/false</td>
			<td>BUSINESS_UNIT_NAME</td>
			<td>This parameter is mandatory only for clients utilizing a multi-organizational solution. 
            ❗<b>Omit this parameter unless instructed about it.</b>❗</br> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data. Each business unit can have its own set of users, permissions, and data access rules. </br><i>(Upcoming feature)</i></td>
		</tr>
        <tr>
            <td><b>BankTitle</b></td>
            <td>String</td>
            <td>false</td>
            <td>TBC bank</td>
            <td>Title of bank with which the operation is happening</td>
        </tr>
        <tr>
            <td><b>AccountExtId</b></td>
            <td>String</td>
            <td>true</td>
            <td>Acc_0011</td>
            <td>External account identification number used to track activity regarding the specific account</td>
        </tr>
        <tr>
            <td><b>AccountNumber</b></td>
            <td>String</td>
            <td>true</td>
            <td>LT705734389447757988</td>
            <td>Unique account identification number used in performing operations</td>
        </tr>
        <tr>
            <td><b>AccountPurpose</b></td>
            <td>String</td>
            <td>false</td>
            <td>PURPOSE_INVEST</td>
            <td>The purpose of owning the account in question</td>
        </tr>
        <tr>
            <td><b>AccountStatus</b></td>
            <td>String<br/><b>ENUM</b><br/> [ACTIVE, <br/>SUSPENDED,<br/> CLOSED]</td>
            <td>true</td>
            <td>ACTIVE</td>
            <td>Refers to the current condition or state of an account</td>
        </tr>
        <tr>
            <td><b>AccountType</b></td>
			<td>
                String <br/>
                <a href="../../Classifiers/classifiers.md">(Account type classifier)</a>
            </td>
            <td>false</td>
            <td>ORG_B2B</td>
            <td>Categorizes accounts by their intended purposes and features</td>
        </tr>
        <tr>
            <td><b>BIC</b></td>
            <td>String</td>
            <td>true</td>
            <td>BICXX22</td>
            <td>Bank identifier code for account number</td>
        </tr>
        <tr>
            <td><b>BusinessEntityExtId</b></td>
            <td>String</td>
            <td>true</td>
            <td>ExtId_0012</td>
            <td>External business entity indicator. Refers to the same value used for the <br/><b>customerExtId</b>, which helps to identify external business entity</td>
        </tr>
        <tr>
            <td><b>OpeningDate</b></td>
            <td>Date</td>
            <td>true</td>
            <td>2022-12-10T12:10:11+02:00</td>
            <td>Account opening date</td>
        </tr>
        <tr>
            <td><b>ClosingDate</b></td>
            <td>Date</td>
            <td>true/false</td>
            <td>2022-12-11T12:10:11+02:00</td>
            <td>Account closing date <br/> <b>Mandatory</b> only when accountStatus = CLOSED</td>
        </tr>
        <tr>
            <td><b>CurrencyCode</b></td>
            <td>
                String <br/>
                <a href="../../Classifiers/classifiers.md">(Currency classifier)</a>
            </td>
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
            <td><b>SuspensionReasons</b></td>
            <td>String</td>
            <td>false</td>
            <td>Security breach investigation in progress</td>
            <td>A reason for suspension can be provided only if the account status is SUSPENDED</td>
        </tr>
    </tbody>
</table>
