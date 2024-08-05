# INDIVIDUAL Fields 

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
			<td><b>Example</b></td>
			<td width="600px"><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td><b>communicationNumber</b></td>
			<td>String</td>
			<td>true</td>
			<td>ComNr_000321</td>
			<td>Unique number of communication. Used for risk assessment callback. This field can store up to 256 characters</td>
		</tr>
		<tr>
			<td><b>requester</b></td>
			<td>String</td>
			<td>true</td>
			<td>AMLYZE_SYSTEM</td>
			<td>Name of the system requesting web service</td>
		</tr>
		<tr>
			<td><b>riskManagementCategory</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Risk management category classifier)</a>
            </td>
			<td>true</td>
			<td>OCCASIONAL_CUSTOMER</td>
			<td>
                Code of risk management category for evaluation of the object.<br/>💡 
                Possible values here are given just as an example, in the configuration period these could be updated
            </td>
		</tr>
		<tr>
			<td><b>entityType</b></td>
			<td>String<br/><b>ENUM</b><br/>[INDIVIDUAL]</td>
			<td>true</td>
			<td>INDIVIDUAL</td>
			<td>Whether business or individual entity</td>
		</tr>
		<tr>
			<td><b>customerExtId</b></td>
			<td>String</td>
			<td>true</td>
			<td>IND20231117550</td>
			<td>Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution</td>
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
            ❗<b>Omit this parameter unless instructed about it.</b>❗<br/> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data. Each business unit can have its own set of users, permissions, and data access rules. <br/><i>(Upcoming feature)</i></td>
		</tr>
		<tr>
			<td><b>customerStatus</b></td>
			<td>String<br/><b>ENUM</b><br/>[PENDING,<br/>ACTIVE,<br/> REJECTED,<br/> SUSPENDED,<br/>CLOSED]</td>
			<td>false</td>
			<td>ACTIVE</td>
			<td>Customer status represents the current standing or state of a customer's relationship with a business or organization <br/> <i> PENDING - Customer application is received.<br/> ACTIVE - Customer is onboarded ( account is provided or customer assessment case is resolved)<br/> REJECTED - the customer for some reasons was rejected before opening an account for him. <br/>SUSPENDED - Customer's activities for some reasons are restricted <br/> CLOSED - Customer's profile is changed to being disabled</i></td>
		</tr>
		<tr>
			<td><b>riskLevel</b></td>
			<td>String<br/><b>ENUM</b><br/>[NONE,<br/> LOW,<br/> MEDIUM,<br/> HIGH,<br/> EXTREME]</td>
			<td>false</td>
			<td>HIGH</td>
			<td>The Risk Level of the customer during IMPORT</td>
		</tr>
        <tr>
            <td><b>initializeScreeningProcesses</b></td>
            <td>String[]</td>
            <td>false</td>
            <td>PEP,<br/>ADVERSE_MEDIA,<br/> SANCTIONS, <br/>INTERNAL_LIST</td>
            <td>Defines which lists to check during screening process</td>
        </tr>
		<tr>
			<td><b>nationalCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>REG74121101</td>
			<td>National code or national identification number of individual. If a country does not issue national code, any other unique identifier can be used:<br/> <i>* Passport number;<br/>* Social security number of person; <br/> * A number of taxpayer or registration certificate of the company, etc <br/> * A number of taxpayer or registration certificate of the company</i></td>
		</tr>
		<tr>
			<td><b>applicationDate</b></td>
			<td>Date</td>
			<td>true</td>
			<td>2000-01-03</td>
			<td>Date when customer first applied</td>
		</tr>
		<tr>
			<td><b>activityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>financial activity</td>
			<td>Description of entity activity</td>
		</tr>
		<tr>
			<td><b>amlOfficer</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the person being AML officer</td>
		</tr>
		<tr>
			<td><b>listPurpose</b></td>
			<td>String<br/><b>ENUM</b><br/>[BLACK,<br/> WHITE]</td>
			<td>false</td>
			<td>-</td>
			<td>Whether entity is black/white listed</td>
		</tr>
		<tr>
			<td><b>approvalDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2000-01-03</td>
			<td>Date of application approval</td>
		</tr>
		<tr>
			<td><b>birthCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of birth of individual entity</td>
		</tr>
		<tr>
			<td><b>birthDate</b></td>
			<td>Date</td>
			<td>true</td>
			<td>1995-05-24</td>
			<td>Date of birth of individual entity</td>
		</tr>
		<tr>
			<td><b>citizenshipCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of citizenship of individual entity</td>
		</tr>
		<tr>
			<td><b>closingDate</b></td>
			<td>Date</td>
			<td>true/false</td>
			<td>2015-05-24</td>
			<td>Date of closure of all accounts <br/><b>Mandatory</b> when customerStatus = CLOSED<br/><b>Not Mandatory</b>  when customerStatus = PENDING, ACTIVE, REJECTED, SUSPENDED</td>
		</tr>
        <tr>
			<td><b>doesCashDominate</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for cash being the main income source</td>
		</tr>
        <tr>
			<td><b>firstName</b></td>
			<td>String</td>
			<td>true</td>
			<td>Jose</td>
			<td>First name of individual entity</td>
		</tr>
        <tr>
			<td><b>lastName</b></td>
			<td>String</td>
			<td>true</td>
			<td>Rodriguez</td>
			<td>Last name of individual entity</td>
		</tr>
        <tr>
			<td><b>incomeSourceDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>work</td>
			<td>Description of income source of the entity</td>
		</tr>
		<tr>
			<td><b>initialDepositAccount</b></td>
			<td>String</td>
			<td>false</td>
			<td>LT0057800085008800</td>
			<td>Account of initial deposit</td>
		</tr>
		<tr>
			<td><b>initialDepositAmount</b></td>
			<td>Double</td>
			<td>false</td>
			<td>10000</td>
			<td>Amount of initial deposit</td>
		</tr>
		<tr>
			<td><b>initialDepositBank</b></td>
			<td>String</td>
			<td>false</td>
			<td>BankBank</td>
			<td>Bank of the initial deposit</td>
		</tr>
		<tr>
			<td><b>initialDepositCurrency</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Currency classifier)</a>
            </td>
			<td>false</td>
			<td>EUR</td>
			<td>Currency field notifies about the currency used in a certain operation.</td>
		</tr>
		<tr>
			<td><b>initialDepositSource</b></td>
			<td>String</td>
			<td>false</td>
			<td>Dividend</td>
			<td>Source of initial deposit</td>
		</tr>
        <tr>
			<td><b>isActualAddressDeclared</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Whether customer declared ActualAddress</td>
		</tr>
        <tr>
			<td><b>isFamilyPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Identification of whether a family member of an Individual entity is politically exposed</td>
		</tr>
        <tr>
			<td><b>isInAdverseMedia</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>An indication of the existence of information for an adverse media entity</td>
		</tr>
        <tr>
			<td><b>isInInternalList</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>An indication of the existence of information for an internal list entity</td>
		</tr>
		<tr>
			<td><b>isLegalResident</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for whether individual entity is a legal resident</td>
		</tr>
        <tr>
			<td><b>isLitigated</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the person being litigated</td>
		</tr>
		<tr>
			<td><b>isPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Identification for whether a person is politically exposed</td>
		</tr>
        <tr>
			<td><b>isSanctioned</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Whether entity is sanctioned</td>
		</tr>
        <tr>
			<td><b>permanentResidenceCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of permanent residency of an individual entity</td>
		</tr>
        <tr>
			<td><b>secondCitizenshipCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of second citizenship of individual entity</td>
		</tr>
		<tr>
			<td><b>listAddress</b></td>
            <td><a href="#AddressApi">AddressApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of addresses</td>
		</tr>
		<tr>
			<td><b>listBusinessEntityDocument</b></td>
            <td><a href="#BusinessEntityDocumentApi">BusinessEntityDocumentApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of related entity documents</td>
		</tr>
		<tr>
			<td><b>listContact</b></td>
            <td><a href="#ContactApi">ContactApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of contacts of related entity</td>
		</tr>
	</tbody>
</table>

---

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
			<td>SANCTIONS,<br/>PEP,<br/> ADVERSE_MEDIA</td>
		</tr>
	</tbody>
</table>


## Address

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
			<td><b>addressDetails</b></td>
			<td>String</td>
			<td>true</td>
			<td>Verkiu 1, Vilnius</td>
			<td>Full address description</td>
	    </tr>
	    <tr>
			<td><b>addressType</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Address type classifier)</a>
            </td>
			<td>false</td>
			<td>RESIDENCE</td>
			<td>Type of entity address.</td>
	    </tr>
	    <tr>
			<td><b>city</b></td>
			<td>String</td>
			<td>false</td>
			<td>Vilnius</td>
			<td>City of given address</td>
	    </tr>
	    <tr>
			<td><b>country</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Country type classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of given address.</td>
	    </tr>
	    <tr>
			<td><b>region</b></td>
			<td>String</td>
			<td>false</td>
			<td>EU</td>
			<td>Region of given address</td>
	    </tr>
	    <tr>
			<td><b>streetAddress</b></td>
			<td>String</td>
			<td>false</td>
			<td>Verkiu 1</td>
			<td>Street, house and flat of given address</td>
	    </tr>
	    <tr>
			<td><b>useForCorrespondence</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Check for using the address in correspondence</td>
	    </tr>
	    <tr>
			<td><b>zipCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>12345</td>
			<td>Zip code of the address</td>
	    </tr>
	</tbody>
</table>


## BusinessEntityDocument

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
			<td><b>description</b></td>
			<td>String</td>
			<td>false</td>
			<td>passport</td>
			<td>Document description</td>
	    </tr>
	    <tr>
			<td><b>documentExpiryDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2032-01-15</td>
			<td>The expiry date of the document in question</td>
	    </tr>
	    <tr>
			<td><b>documentIssueAuthority</b></td>
			<td>String</td>
			<td>true</td>
			<td>migration office</td>
			<td>An authority that issued the document.</td>
	    </tr>
	    <tr>
			<td><b>documentIssueCountry</b></td>
			<td>String</td>
			<td>true</td>
			<td>LT</td>
			<td>A country that issued the document</td>
	    </tr>
	    <tr>
			<td><b>documentIssueDate</b></td>
			<td>Date</td>
			<td>true</td>
			<td>2022-01-15</td>
			<td>Issue date of the document in question</td>
	    </tr>
	    <tr>
			<td><b>documentNumber</b></td>
			<td>String</td>
			<td>true</td>
			<td>0123456789</td>
			<td>Number of document in question</td>
	    </tr>
	    <tr>
			<td><b>entityType</b></td>
			<td>String<br/><b>ENUM</b><br/> [INDIVIDUAL, <br/> ORGANIZATION]</td>
			<td>true</td>
			<td>INDIVIDUAL</td>
			<td>Entity type describes client status</td>
	    </tr>
	    <tr>
			<td><b>identityDocumentType</b></td>
			<td>String<br/><b>ENUM</b><br/>[PASSPORT, <br/> IDENTITYCARD,<br/> RESIDENCEPERMIT,<br/> DRIVINGLICENSE,<br/> REGISTRATIONCERTIFICATE,<br/> OTHER]</td>
			<td>true</td>
			<td>PASSPORT</td>
			<td>Identification document</td>
	    </tr>
	</tbody>
</table>

## Contact

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
			<td><b>contactType</b></td>
            <td>String<br/><b>ENUM</b><br/>[MOBILEPHONE, <br/>FIXEDPHONE, <br/>EMAIL,WEBSITE]</td>
			<td>true</td>
			<td>MOBILEPHONE</td>
			<td>Way of contacting entity.</td>
	    </tr>
	    <tr>
			<td><b>contactDetails</b></td>
			<td>String</td>
			<td>true</td>
			<td>
                868758585<br/>
                hello@gmail.com<br/>
                www.website.com<br/>
            </td>
			<td>Details of contact.</td>
	    </tr>
	    <tr>
			<td><b>useForCommunication</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true/false</td>
			<td>Indicator for the usage of communication way.</td>
	    </tr>
	</tbody>
</table>


