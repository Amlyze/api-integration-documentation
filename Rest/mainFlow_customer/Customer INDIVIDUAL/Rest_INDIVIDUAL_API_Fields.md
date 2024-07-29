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
			<td>Test_ComNr_002mHzZZ</td>
			<td>Unique number of communication. Used for risk assessment callback. This field can store up to 256 characters</td>
		</tr>
		<tr>
			<td><b>requester</b></td>
			<td>String</td>
			<td>true</td>
			<td>Company Name Amlyze</td>
			<td>Name of the system requesting web service</td>
		</tr>
		<tr>
			<td><b>action</b></td>
			<td>String<br/><b>ENUM</b><br/>[CREATE (<i>default</i>), <br/> UPDATE]</td>
			<td>false</td>
			<td>UPDATE</td>
			<td>Element is used to change data of the existing Customer. <br/>❗ NOTE: all data will be replaced with newly received one</td>
		</tr>
		<tr>
			<td><b>sourceOfRiskLevel</b></td>
			<td>String<br/><b>ENUM</b><br/>[IMPORT, EVALUATE]</td>
			<td>true</td>
			<td>IMPORT</td>
			<td>The value <b>EVALUATE</b> is used for initiating a customer risk assessment.<br/> The value <b>IMPORT</b> is used for customer import or customer data updates where initiation of new risk assessment is not needed. This typically applies to customer migration or updating customer data that do not affect customer risk level and automatic customer reassessment is not needed.</td>
		</tr>
		<tr>
			<td><b>riskLevel</b></td>
			<td>String<br/><b>ENUM</b><br/>[NONE,<br/> LOW,<br/> MEDIUM,<br/> HIGH,<br/> EXTREME]</td>
			<td>true/false</td>
			<td>HIGH</td>
			<td>
                Customer's predefined  risk based on historical data <br/><b>Mandatory</b> when sourceOfRiskLevel = IMPORT<br/>
                <b>Not used</b>  when sourceOfRiskLevel = EVALUATE</td>
		</tr>
		<tr>
			<td><b>customerStatus</b></td>
			<td>String<br/><b>ENUM</b><br/>[PENDING,<br/>ACTIVE,<br/> REJECTED,<br/> SUSPENDED,<br/>CLOSED]</td>
			<td>true/false</td>
			<td>ACTIVE</td>
			<td>Customer's predefined status represents the current standing or state of a customer's relationship with a business or organization <br/> <i> PENDING - Customer application is received but not yet prepared for upcoming workflow <br/> ACTIVE - Customer is onboarded and ready for workflow <br/> REJECTED - the customer for some reasons was rejected before opening an account for him. <br/>SUSPENDED - Customer's activities for some reasons are restricted <br/> CLOSED - Customer's profile is disabled</i></br> <b>Mandatory</b> when sourceOfRiskLevel = IMPORT<br/> <b>Not Used</b>  when sourceOfRiskLevel = EVALUATE</td>
		</tr>
		<tr>
			<td><b>initializeScreeningProcesses</b></td>
			<td>String[]</td>
			<td>false</td>
            <td>SANCTIONS,<br/>PEP,<br/> ADVERSE_MEDIA <br/> INTERNAL_LIST</td>
			<td>Defines which screening processes to initiate</td>
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
			<td><b>riskManagementCategory</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Risk management category classifier)</a>
            </td>
			<td>true</td>
			<td>IND_AMLYZE</td>
			<td>
                Code of risk management category for evaluation of the object.<br/>💡 
                Possible value here is given just as an example
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
			<td>cust_1232</td>
			<td>Unique external customer identifier. Identifier corresponds to the client's identifier in the financial institution</td>
		</tr>
		<tr>
			<td><b>applicationDate</b></td>
			<td>Date</td>
			<td>true</td>
			<td>2000-01-03</td>
			<td>Date when customer first applied</td>
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
			<td><b>birthDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2000-01-01</td>
			<td>Date of birth of individual entity</td>
		</tr>
		<tr>
			<td><b>approvalDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2023-10-01T09:45:00.000+02:00</td>
			<td>Date of application approval</td>
		</tr>
		<tr>
			<td><b>closingDate</b></td>
			<td>Date</td>
			<td>true/false</td>
			<td>1995-05-24</td>
			<td>Date of closure of all accounts <br/><b>USED</b> when customerStatus = CLOSED<br/><b>Not Used</b>  when customerStatus = PENDING, ACTIVE, REJECTED, SUSPENDED</td>
		</tr>
		<tr>
			<td><b>birthCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of birth of individual entity</td>
		</tr>
		<tr>
			<td><b>nationalCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>50001010022</td>
			<td>National code or national identification number of individual. If a country does not issue national code, any other unique identifier can be used:<br/> <i>* Passport number;<br/>* Social security number of person; <br/> * A number of taxpayer or registration certificate of the company, etc <br/> * A number of taxpayer or registration certificate of the company</i></td>
		</tr>
		 <tr>
			<td><b>secondCitizenshipCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LV</td>
			<td>Country of second citizenship of individual entity</td>
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
			<td><b>isLegalResident</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for whether individual entity is a legal resident</td>
		</tr>
		<tr>
			<td><b>isPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
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
			<td><b>isInAdverseMedia</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>An indication of the existence of information for an adverse media entity</td>
		</tr>
		 <tr>
			<td><b>isFamilyPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Identification of whether a family member of an Individual entity is politically exposed</td>
		</tr>
        <tr>
			<td><b>isLitigated</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the person being litigated</td>
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
			<td>WHITE</td>
			<td>Whether entity is black/white listed</td>
		</tr>
		<tr>
			<td><b>fieldOfActivity</b></td>
            <td><a href="#FieldOfActivityApi">[FieldOfActivityApi]</a></td>
			<td>false</td>
			<td>-</td>
			<td>Information about the activities</td>
		</tr>
		<tr>
			<td><b>isActualAddressDeclared</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Whether customer declared ActualAddress</td>
		</tr>
		<tr>
			<td><b>isCorrespondenceAddressDeclared</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Whether customer declared CorrespondenceAddress</td>
		</tr>
		<tr>
			<td><b>activityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Financial activity</td>
			<td>Description of entity activity</td>
		</tr>
		<tr>
			<td><b>incomeSourceDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Job salary</td>
			<td>Description of income source of the entity</td>
		</tr>
		<tr>
			<td><b>initialDepositSource</b></td>
			<td>String</td>
			<td>false</td>
			<td>Salary</td>
			<td>Source of initial deposit</td>
		</tr>
		<tr>
			<td><b>initialDepositBank</b></td>
			<td>String</td>
			<td>false</td>
			<td>TBC</td>
			<td>Bank of the initial deposit</td>
		</tr>
		<tr>
			<td><b>initialDepositAccount</b></td>
			<td>String</td>
			<td>false</td>
			<td>LT0089500500000070</td>
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
			<td><b>doesCashDominate</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for cash being the main income source</td>
		</tr>
		<tr>
			<td><b>listContact</b></td>
            <td><a href="#ContactApi">ContactApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of contacts</td>
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
			<td>List of business entity documents</td>
		</tr>
		<tr>
			<td><b>listAppealReason</b></td>
            <td><a href="#AppealReasonApi">AppealReasonApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of reasons for the appeal</td>
		</tr>
		<tr>
			<td><b>listIntroductionSource</b></td>
            <td><a href="#IntroductionSourceApi">IntroductionSourceApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of sources of introduction</td>
		</tr>
		<tr>
			<td><b>listOrderedService</b></td>
            <td><a href="#OrderedServiceApi">OrderedServiceApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of ordered services</td>
		</tr>
		<tr>
			<td><b>listDeclaredTurnover</b></td>
            <td><a href="#DeclaredTurnoverApi">DeclaredTurnoverApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of declared turnover</td>
		</tr>
		<tr>
			<td><b>listIncomeSource</b></td>
			<td><a href="#IncomeSourceApi">IncomeSourceApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of countries of payment</td>
		</tr>
		<tr>
			<td><b>listPaymentPurpose</b></td>
            <td><a href="#PaymentPurposeApi">PaymentPurposeApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of payment purpose</td>
		</tr>
		<tr>
			<td><b>listSourceOfWealth</b></td>
            <td><a href="#SourceOfWealthApi">SourceOfWealthApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of wealth sources</td>
		</tr>
		<tr>
			<td><b>listPaymentCountry</b></td>
            <td><a href="#PaymentCountryApi">PaymentCountryApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of payment country</td>
		</tr>
		<tr>
			<td><b>listActivity</b></td>
			<td><a href="#ActivityApi">ActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activities</td>
		</tr>
		<tr>
			<td><b>listRegionOfActivity</b></td>
            <td><a href="#RegionOfActivityApi">RegionOfActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activity countries of business entity</td>
		</tr>
		<tr>
			<td><b>listCountryOfActivity</b></td>
            <td><a href="#CountryOfActivityApi">CountryOfActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activity regions</td>
		</tr>
		<tr>
			<td><b>listCountryOfTaxPayment</b></td>
            <td><a href="#CountryOfTaxPaymentApi">CountryOfTaxPaymentApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of tax payment country</td>
		</tr>
		<tr>
			<td><b>listAdditionalValues</b></td>
			<td><a href="#AdditionalValueApi">AdditionalValueApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>Additional information about businessEntity</td>
		</tr>
		<tr>
			<td><b>listRelatedEntity</b></td>
            <td><a href="#RelatedEntityApi">RelatedEntityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List for related business entities</td>
		</tr>
	</tbody>
</table>

---

## FieldOfActivityApi

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>employment</b></td>
			<td>FieldEmploymentApi</td>
			<td>false</td>
		</tr>
		<tr>
			<td><b>other</b></td>
			<td>FieldOtherApi</td>
			<td>false</td>
		</tr>
		<tr>
			<td><b>pension</b></td>
			<td>FieldPensionApi</td>
			<td>false</td>
		</tr>
		<tr>
			<td><b>student</b></td>
			<td>FieldStudentApi</td>
			<td>false</td>
		</tr>
	</tbody>
</table>

## FieldEmploymentApi

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
			<td><b>employerTitle</b></td>
			<td>String</td>
			<td>false</td>
			<td>CompanyB</td>
			<td>Title of the individual employer.</td>
		</tr>
		<tr>
			<td><b>employmentPositionDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Software Engineer</td>
			<td>Description of the individual employment position.</td>
		</tr>
		<tr>
			<td><b>isEmployee</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the individual entity being an employee</td>
		</tr>
		<tr>
			<td><b>isSelfEmployed</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the individual entity being self-employed</td>
		</tr>
		<tr>
			<td><b>isUnemployed</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the individual entity being unemployed</td>
		</tr>
	</tbody>
</table>



## FieldOtherApi

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
			<td><b>isOtherStatus</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for other status individual</td>
	    </tr>
	    <tr>
			<td><b>otherStatusDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>consultation</td>
			<td>Description of other status</td>
	    </tr>
	</tbody>
</table>


## FieldPensionApi

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
			<td><b>isPensioner</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for the individual entity being a pensioner</td>
	    </tr>
	    <tr>
			<td><b>pensionCountry</b></td>
			<td>String</td>
			<td>false</td>
			<td>LT</td>
			<td>The country is responsible for paying an individual's pension</td>
	    </tr>
	</tbody>
</table>


## FieldStudentApi

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
			<td><b>higherSchoolCountry</b></td>
			<td>String</td>
			<td>false</td>
			<td>LT</td>
			<td>Indicator for individual entity being a student</td>
	    </tr>
	    <tr>
			<td><b>higherSchoolTitle</b></td>
			<td>String</td>
			<td>false</td>
			<td>Vilniaus Universitetas MIF</td>
			<td>Title of higher school of the student</td>
	    </tr>
	    <tr>
			<td><b>isStudent</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Country of higher school of the student</td>
	    </tr>
	</tbody>
</table>

## ContactApi

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

## AddressApi

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
			<td>false</td>
			<td>Building B</td>
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
			<td>Verkių g. 1-9, Vilnius</td>
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


## BusinessEntityDocumentApi

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
			<td>Migration office</td>
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

## AppealReasonApi

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>appealReasonType</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Appeal reason type classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>

## IntroductionSourceApi

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>introductionSource</b></td>
            <td>
                String <br/>
                <a href="../../README.md#classifiers">(Introduction source classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>

## OrderedServiceApi

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>serviceType</b></td>
            <td>
                String <br/>
                <a href="../../README.md#classifiers">(Service type classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>

## DeclaredTurnoverApi

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
			<td><b>from</b></td>
			<td>BigInteger</td>
			<td>true/false</td>
			<td>1000</td>
			<td>Amount range from. At least one value (from or to) must be specified</td>
	    </tr>
	    <tr>
			<td><b>to</b></td>
			<td>String</td>
			<td>true/false</td>
			<td>5000</td>
			<td>Amount to. At least one value (from or to) must be specified</td>
	    </tr>
	    <tr>
			<td><b>turnoverRange</b></td>
			<td>String<br/><b>ENUM</b><br/> [SINGLE,<br/> DAILY, <br/> MONTHLY,<br/> ANNUAL]</td>
			<td>true</td>
			<td>MONTHLY</td>
			<td>Range of declared turnover</td>
	    </tr>
	    <tr>
			<td><b>turnoverType</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Turnover type classifier)</a>
            </td>
			<td>true</td>
			<td>TURNOVER_PER_MONTH</td>
			<td>Type of declared turnover</td>
	    </tr>
	</tbody>
</table>

## IncomeSourceApi

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
			<td><b>from</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>100</td>
			<td>Amount from</td>
	    </tr>
	    <tr>
			<td><b>incomePercentage</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>5</td>
			<td>Percentage of income from the source</td>
	    </tr>
	    <tr>
			<td><b>incomeSourceType</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Income source type classifier)</a>
            </td>
			<td>true</td>
			<td>SALARY</td>
			<td>Type of income source</td>
	    </tr>
	    <tr>
			<td><b>to</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>1000</td>
			<td>Amount to</td>
	    </tr>
	</tbody>
</table>


## PaymentPurposeApi

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
			<td><b>paymentPurposeType</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Payment purpose type classifier)</a>
            </td>
			<td>true</td>
			<td>TAXES</td>
			<td>Type of income source code.</td>
	    </tr>
	    <tr>
			<td><b>turnoverDirection</b></td>
			<td>String<br/><b>ENUM</b><br/> [IN,<br/>OUT]</td>
			<td>true</td>
			<td>OUT</td>
			<td>The turnover direction of payment</td>
	    </tr>
	</tbody>
</table>

## SourceOfWealthApi

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
			<td><b>amount</b></td>
			<td>BigDecimal</td>
			<td>false</td>
			<td>100000</td>
			<td>Collected monetary amount</td>
	    </tr>
	    <tr>
			<td><b>code</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Source of wealth type classifier)</a>
            </td>
			<td>true</td>
			<td>INHERITANCE</td>
			<td>source of wealth code</td>
	    </tr>
	    <tr>
			<td><b>comment</b></td>
			<td>String</td>
			<td>false</td>
			<td>text</td>
			<td>Additional details about the source of wealth</td>
	    </tr>
	</tbody>
</table>   

## PaymentCountryApi

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
			<td><b>country</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>TAXES</td>
			<td>Type of income source code.</td>
	    </tr>
	    <tr>
			<td><b>turnoverDirection</b></td>
			<td>String<br/><b>ENUM</b><br/> [IN,<br/>OUT]</td>
			<td>true</td>
			<td>OUT</td>
			<td>The turnover direction of payment</td>
	    </tr>
	</tbody>
</table>




## ActivityApi

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
			<td><b>activityType</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Activity type classifier)</a>
            </td>
			<td>true</td>
			<td>ACTIVITY_OTHER</td>
			<td>Type of business activity.</td>
	    </tr>
	    <tr>
			<td><b>incomePercentage</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>15</td>
			<td>Percentage of income from certain activity</td>
	    </tr>
	</tbody>
</table>


## RegionOfActivityApi

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>region</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Country classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>

## CountryOfActivityApi

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>country</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Country classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>


## CountryOfTaxPaymentApi

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
			<td><b>country</b></td>
            <td>
                String <br/>
                <a href="../../README.md#classifiers">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of tax payment</td>
	    </tr>
	    <tr>
			<td><b>taxpayerNumber</b></td>
			<td>String</td>
			<td>false</td>
			<td>5541245574</td>
			<td>The number of tax payer</td>
	    </tr>
	</tbody>
</table>


## AdditionalValueApi

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
			<td><b>code</b></td>
			<td>String</td>
			<td>true</td>
			<td>related_to_usa</td>
			<td>Identifier for additional field</td>
	    </tr>
	    <tr>
			<td><b>datatype</b></td>
			<td>String<br/><b>ENUM</b><br/>[STRING,<br/> INTEGER,<br/> DECIMAL,<br/> DATE,<br/> TIMESTAMP,<br/> BOOLEAN]</td>
			<td>true</td>
			<td>STRING</td>
			<td>Type of provided value</td>
	    </tr>
	    <tr>
			<td><b>description</b></td>
			<td>String</td>
			<td>true</td>
			<td>Entity has relation to USA</td>
			<td>human readable description of field</td>
	    </tr>
	    <tr>
			<td><b>value</b></td>
			<td>String</td>
			<td>true</td>
			<td>true</td>
			<td>value of field</td>
	    </tr>
    </tbody>
</table>


         

## RelatedEntityApi INDIVIDUAL

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
			<td><b>entityType</b></td>
			<td>String<br/><b>ENUM</b><br/> [INDIVIDUAL, <br/>ORGANIZATION]</td>
			<td>true</td>
			<td>INDIVIDUAL</td>
			<td>Entity type describes client status</td>
	    </tr>
	    <tr>
			<td><b>relationType</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Relation type classifier)</a>
            </td>
			<td>true</td>
			<td>OWNER</td>
			<td>Type of relationship between entities.</td>
	    </tr>
		<tr>
			<td><b>relationDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Founder</td>
			<td>Description of the relationship between entities</td>
	    </tr>
		<tr>
			<td><b>extId</b></td>
			<td>String</td>
			<td>false</td>
			<td>Related_extID_000</td>
			<td>Used for screening callbacks to identify entity</td>
	    </tr>
	    <tr>
			<td><b>share</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>75</td>
			<td>Shares owned by shareholders in the organization of the business entity</td>
	    </tr>
	    <tr>
			<td><b>votePercentage</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>99</td>
			<td>Vote percentage of shareholders in the organization of business entity</td>
	    </tr>
		<tr>
			<td><b>nationalCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>123456789</td>
			<td>National code or national identification number of individual or organization. If a country does not issue national code, any other unique identifier can be used</td>
	    </tr>
	    <tr>
			<td><b>activityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Financial activity</td>
			<td>Activity description of the related entity</td>
	    </tr>
		<tr>
			<td><b>country</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Citizenship country of the related entity</td>
	    </tr>
	    <tr>
			<td><b>birthCountry</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>The birth country of the related entity</td>
	    </tr>
		 <tr>
			<td><b>firstName</b></td>
			<td>String</td>
			<td>true/false</td>
			<td>John</td>
			<td>First name of related entity br><b>Mandatory</b> when entityType = INDIVIDUAL <br/><b>Not Used</b>  when entityType = ORGANIZATION</td>
	    </tr>
		<tr>
			<td><b>lastName</b></td>
			<td>String</td>
			<td>true/false</td>
			<td>Rodriguez</td>
			<td>Last name of related entity <br/><b>Mandatory</b> when entityType = INDIVIDUAL <br/><b>Not Used</b>  when entityType = ORGANIZATION</td>
	    </tr>
	    <tr>
			<td><b>birthDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2000-05-28</td>
			<td>Birth date of a related individual entity</td>
	    </tr>
	    <tr>
			<td><b>isPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>An indicator for a related individual entity is a politically exposed person</td>
	    </tr>
	    <tr>
			<td><b>isSanctioned</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for sanctions applied to the entity</td>
	    </tr>
	    <tr>
			<td><b>isInAdverseMedia</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>An indication of the existence of information for an adverse media entity</td>
	    </tr>
	   	<tr>
			<td><b>regionOfActivityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>EU</td>
			<td>Description of activity region of related entity</td>
	    </tr>
		<tr>
			<td><b>listContact</b></td>
            <td><a href="#ContactApi">ContactApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of contacts of related entity</td>
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
			<td>List of related entity document</td>
    	</tr>
	    <tr>
			<td><b>listIncomeSource</b></td>
			<td><a href="#IncomeSourceApi">IncomeSourceApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of income sources</td>
	    </tr>
		<tr>
			<td><b>listActivity</b></td>
            <td><a href="#ActivityApi">ActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activities of related entity</td>
    	</tr>
	    <tr>
			<td><b>listRegionOfActivity</b></td>
            <td><a href="#RegionOfActivityApi">RegionOfActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activity regions of related entity</td>
	    </tr>
		<tr>
			<td><b>listCountryOfActivity</b></td>
            <td><a href="#CountryOfActivityApi">CountryOfActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activity countries of related entity</td>
	    </tr>
		<tr>
			<td><b>listAdditionalValues</b></td>
            <td><a href="#AdditionalValueApi">AdditionalValueApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>Additional information about businessEntity</td>
    	</tr>
	</tbody>
</table>
	    
	    
	    
	    
	    
		
	    
	    
	    
	    
    	
    	
    	
    	


## RelatedEntityApi ORGANIZATION

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
			<td><b>entityType</b></td>
			<td>String<br/><b>ENUM</b><br/> [INDIVIDUAL, <br/>ORGANIZATION]</td>
			<td>true</td>
			<td>INDIVIDUAL</td>
			<td>Entity type describes client status</td>
	    </tr>
	    <tr>
			<td><b>relationType</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Relation type classifier)</a>
            </td>
			<td>true</td>
			<td>OWNER</td>
			<td>Type of relationship between entities.</td>
	    </tr>
		<tr>
			<td><b>relationDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>founder</td>
			<td>Description of the relationship between entities</td>
	    </tr>
		<tr>
			<td><b>extId</b></td>
			<td>String</td>
			<td>false</td>
			<td>12345678912345</td>
			<td>Used for screening callbacks to identify entity</td>
	    </tr>
	    <tr>
			<td><b>share</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>75</td>
			<td>Shares owned by shareholders in the organization of the business entity</td>
	    </tr>
	    <tr>
			<td><b>votePercentage</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>99</td>
			<td>Vote percentage of shareholders in the organization of business entity</td>
	    </tr>
		<tr>
			<td><b>nationalCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>123456789</td>
			<td>National code or national identification number of individual or organization. If a country does not issue national code, any other unique identifier can be used</td>
	    </tr>
	    <tr>
			<td><b>activityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>financial activity</td>
			<td>Activity description of the related entity</td>
	    </tr>
		<tr>
			<td><b>country</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of the related entity</td>
	    </tr>
		<tr>
			<td><b>registrationCountry</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of business operations of related individual entity.</td>
	    </tr>
		<tr>
			<td><b>isPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>An indicator for a related individual entity is a politically exposed person</td>
	    </tr>
	    <tr>
			<td><b>isSanctioned</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for sanctions applied to the entity</td>
	    </tr>
	    <tr>
			<td><b>isInAdverseMedia</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>An indication of the existence of information for an adverse media entity</td>
	    </tr>
	   	<tr>
			<td><b>regionOfActivityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>EU</td>
			<td>Description of activity region of related entity</td>
	    </tr>
		<tr>
			<td><b>title</b></td>
			<td>String</td>
			<td>true/ false</td>
			<td>Beko</td>
			<td><br/><b>Mandatory</b> when entityType = ORGANIZATION <br/><b>Not Used</b>  when entityType = INDIVIDUAL</td>
	    </tr>
		<tr>
			<td><b>legalForm</b></td>
			<td>
                String <br/>
                <a href="../../README.md#classifiers">(Legal form classifier)</a>
            </td>
			<td>false</td>
			<td>COOPERATIVE</td>
			<td>Legal form of organization</td>
	    </tr>
		<tr>
			<td><b>establishmentDate</b></td>
			<td>Date</br><b>Format: ISO 8601</b></br><b>YYYY-MM-DD</b></td>
			<td>false</td>
			<td>1998-04-07</td>
			<td>Establishment date of related organization entity.</td>
	    </tr>
		<tr>
			<td><b>listContact</b></td>
            <td><a href="#ContactApi">ContactApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of contacts of related entity</td>
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
			<td>List of related entity document</td>
    	</tr>
	    <tr>
			<td><b>listIncomeSource</b></td>
			<td><a href="#IncomeSourceApi">IncomeSourceApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of income sources</td>
	    </tr>
		<tr>
			<td><b>listActivity</b></td>
            <td><a href="#ActivityApi">ActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activities of related entity</td>
    	</tr>
	    <tr>
			<td><b>listRegionOfActivity</b></td>
            <td><a href="#RegionOfActivityApi">RegionOfActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activity regions of related entity</td>
	    </tr>
		<tr>
			<td><b>listCountryOfActivity</b></td>
            <td><a href="#CountryOfActivityApi">CountryOfActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activity countries of related entity</td>
	    </tr>
		<tr>
			<td><b>listAdditionalValues</b></td>
            <td><a href="#AdditionalValueApi">AdditionalValueApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>Additional information about businessEntity</td>
    	</tr>
	</tbody>
</table>
