# INDIVIDUAL Fields 

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
			<td><b>Example/Ref</b></td>
			<td width="600px"><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>CommunicationNumber</b></td>
			<td>String</td>
			<td>true</td>
			<td>ComNr_000321</td>
			<td>Unique number of communication. used for risk assessment callback. This field can store up to 256 characters</td>
		</tr>
		<tr>
			<td><b>Requester</b></td>
			<td>String</td>
			<td>true</td>
			<td>financial_institution</td>
			<td>Name of the system requesting web service</td>
		</tr>
		<tr>
			<td><b>Action</b></td>
			<td>String<br/><b>ENUM</b><br/>[CREATE (<i>default</i>), <br/> UPDATE]</td>
			<td>false</td>
			<td>UPDATE</td>
			<td>Element is used to change the data of an existing Customer. <br/>❗ NOTE: all data will be replaced with newly received ones</td>
		</tr>
		<tr>
			<td><b>RiskManagementCategory</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Risk management category classifier)</a>
            </td>
			<td>true</td>
			<td>LEAD_AMLYZE</td>
			<td>
                Code of risk management category for evaluation of the object.<br/>💡 
                Possible values here are given just as an example, in the configuration period these could be updated
            </td>
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
			<td><b>SourceOfRiskLevel</b></td>
			<td>String<br/><b>ENUM</b><br/>[EVALUATE]</td>
			<td>true</td>
			<td>IMPORT</td>
			<td>
                Source of risk level<br/> The value <b>"EVALUATE"</b> 
                should be used for normal business processes - risk assessment will be performed
            </td>
		</tr>
		<tr>
			<td><b>InitializeScreeningProcesses</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#Process">Process[]</a></td>
			<td>Defines which screening processes to initiate</td>
		</tr>
		<tr>
			<td><b>CustomerExtId</b></td>
			<td>String</td>
			<td>true</td>
			<td>cust_1232</td>
			<td>Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution</td>
		</tr>
		<tr>
			<td><b>EntityType</b></td>
			<td>String<br/><b>ENUM</b><br/>[INDIVIDUAL]</td>
			<td>true</td>
			<td>INDIVIDUAL</td>
			<td>Whether business or individual entity</td>
		</tr>
		<tr>
			<td><b>NationalCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>REG74121101</td>
			<td>National code or national identification number of individual. If a country does not issue national code, any other unique identifier can be used:<br/> <i>* Passport number;<br/>* Social security number of person; <br/> * A number of taxpayer or registration certificate of the company, etc <br/> * A number of taxpayer or registration certificate of the company</i></td>
		</tr>
		<tr>
			<td><b>ApplicationDate</b></td>
			<td>Date</td>
			<td>true</td>
			<td>2000-01-03</td>
			<td>Date when customer first applied</td>
		</tr>
		<tr>
			<td><b>ActivityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>financial activity</td>
			<td>Description of entity activity</td>
		</tr>
		<tr>
			<td><b>ActivityInRestrictedRegionDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>logistics</td>
			<td>Description of business entities' activities in a restricted region</td>
		</tr>
		<tr>
			<td><b>AmlOfficer</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the person being AML officer</td>
		</tr>
		<tr>
			<td><b>ApprovalDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2000-01-03</td>
			<td>Date of application approval</td>
		</tr>
		<tr>
			<td><b>BirthCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of birth of individual entity</td>
		</tr>
		<tr>
			<td><b>BirthDate</b></td>
			<td>Date</td>
			<td>true</td>
			<td>1995-05-24</td>
			<td>Date of birth of individual entity</td>
		</tr>
		<tr>
			<td><b>CitizenshipCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of citizenship of individual entity</td>
		</tr>
		<tr>
			<td><b>ClosingDate</b></td>
			<td>Date</td>
			<td>true/false</td>
			<td>1995-05-24</td>
			<td>Date of closure of all accounts <br/><b>Mandatory</b> when customerStatus = CLOSED<br/><b>Not Mandatory</b>  when customerStatus = PENDING, ACTIVE, REJECTED, SUSPENDED</td>
		</tr>
        <tr>
			<td><b>DoesCashDominate</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for cash being the main income source</td>
		</tr>
        <tr>
			<td><b>FirstName</b></td>
			<td>String</td>
			<td>true</td>
			<td>Jose</td>
			<td>First name of individual entity</td>
		</tr>
        <tr>
			<td><b>LastName</b></td>
			<td>String</td>
			<td>true</td>
			<td>Rodriguez</td>
			<td>Last name of individual entity</td>
		</tr>
        <tr>
			<td><b>IncomeSourceDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>work</td>
			<td>Description of income source of the entity</td>
		</tr>
		<tr>
			<td><b>IncomingPaymentDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>payment for work</td>
			<td>Description of incoming payment operation</td>
		</tr>
		<tr>
			<td><b>InitialDepositAccount</b></td>
			<td>String</td>
			<td>false</td>
			<td>LT0000000000000000</td>
			<td>Account of initial deposit</td>
		</tr>
		<tr>
			<td><b>InitialDepositAmount</b></td>
			<td>Double</td>
			<td>false</td>
			<td>10000</td>
			<td>Amount of initial deposit</td>
		</tr>
		<tr>
			<td><b>InitialDepositBank</b></td>
			<td>String</td>
			<td>false</td>
			<td>BankBank</td>
			<td>Bank of the initial deposit</td>
		</tr>
		<tr>
			<td><b>InitialDepositCurrency</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Currency classifier)</a>
            </td>
			<td>false</td>
			<td>EUR</td>
			<td>Currency field notifies about the currency used in a certain operation.</td>
		</tr>
		<tr>
			<td><b>InitialDepositSource</b></td>
			<td>String</td>
			<td>false</td>
			<td>Dividend</td>
			<td>Source of initial deposit</td>
		</tr>
		<tr>
			<td><b>IsActualAddressDeclared</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Whether customer declared ActualAddress</td>
		</tr>
        <tr>
			<td><b>IsFamilyPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Identification of whether a family member of an Individual entity is politically exposed</td>
		</tr>
        <tr>
			<td><b>IsInAdverseMedia</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>An indication of the existence of information for an adverse media entity</td>
		</tr>
		<tr>
			<td><b>IsLegalResident</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for whether individual entity is a legal resident</td>
		</tr>
        <tr>
			<td><b>IsLitigated</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the person being litigated</td>
		</tr>
		<tr>
			<td><b>IsPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Identification for whether a person is politically exposed</td>
		</tr>
        <tr>
			<td><b>IsSanctioned</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Whether entity is sanctioned</td>
		</tr>
        <tr>
			<td><b>PermanentResidenceCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of permanent residency of an individual entity</td>
		</tr>
        <tr>
			<td><b>SecondCitizenshipCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of second citizenship of individual entity</td>
		</tr>
        <tr>
			<td><b>ListPurpose</b></td>
			<td>String<br/><b>ENUM</b><br/>[BLACK,<br/> WHITE]</td>
			<td>false</td>
			<td>-</td>
			<td>Whether entity is black/white listed</td>
		</tr>
		<tr>
			<td><b>FieldOfActivity</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#FieldOfActivity">FieldOfActivity</a></td>
			<td>Information about the activities</td>
		</tr>
		<tr>
			<td><b>ListActivity</b></td>
			<td>Object</td>
			<td>false</td>
			<td><a href="#Activity">Activity[]</a></td>
			<td>List of activities</td>
		</tr>
		<tr>
			<td><b>ListAdditionalValues</b></td>
			<td>Object</td>
			<td>false</td>
			<td><a href="#AdditionalValue">AdditionalValue[]</a></td>
			<td>Additional information about businessEntity</td>
		</tr>
		<tr>
			<td><b>ListAddress</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#Address">Address[]</a></td>
			<td>List of addresses</td>
		</tr>
		<tr>
			<td><b>ListAppealReason</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#AppealReason">AppealReason[]</a></td>
			<td>List of reasons for the appeal</td>
		</tr>
		<tr>
			<td><b>ListBusinessEntityDocument</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#BusinessEntityDocument">BusinessEntityDocument[]</a></td>
			<td>List of related entity documents</td>
		</tr>
		<tr>
			<td><b>ListContact</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#Contact">Contact[]</a></td>
			<td>List of contacts of related entity</td>
		</tr>
		<tr>
			<td><b>ListCountryOfActivity</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#CountryOfActivity">CountryOfActivity[]</a></td>
			<td>List of activity regions</td>
		</tr>
		<tr>
			<td><b>ListCountryOfTaxPayment</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#CountryOfTaxPayment">CountryOfTaxPayment[]</a></td>
			<td>List of tax payment country</td>
		</tr>
		<tr>
			<td><b>ListDeclaredTurnover</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#DeclaredTurnover">DeclaredTurnover[]</a></td>
			<td>List of declared turnover</td>
		</tr>
		<tr>
			<td><b>ListIncomeSource</b></td>
			<td>Object</td>
			<td>false</td>
			<td><a href="#IncomeSource">IncomeSource[]</a></td>
			<td>List of countries of payment</td>
		</tr>
		<tr>
			<td><b>ListIntroductionSource</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#IntroductionSource">IntroductionSource[]</a></td>
			<td>List of sources of introduction</td>
		</tr>
		<tr>
			<td><b>ListOrderedService</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#OrderedService">OrderedService[]</a></td>
			<td>List of ordered services</td>
		</tr>
		<tr>
			<td><b>ListPaymentCountry</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#PaymentCountry">PaymentCountry[]</a></td>
			<td>List of payment country</td>
		</tr>
		<tr>
			<td><b>ListPaymentPurpose</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#PaymentPurpose">PaymentPurpose[]</a></td>
			<td>List of payment purpose</td>
		</tr>
		<tr>
			<td><b>ListRegionOfActivity</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#RegionOfActivity">RegionOfActivity[]</a></td>
			<td>List of activity countries of related entity</td>
		</tr>
		<tr>
			<td><b>ListSourceOfWealth</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#SourceOfWealth">SourceOfWealth[]</a></td>
			<td>List of wealth sources</td>
		</tr>
		<tr>
			<td><b>ListRelatedEntity</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#RelatedEntity">RelatedEntity[]</a></td>
			<td>List for related business entities</td>
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
			<td>SANCTIONS,<br/>PEP,<br/> ADVERSE_MEDIA,<br>INTERNAL_LIST</td>
		</tr>
	</tbody>
</table>

## AppealReason

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
			<td><b>AppealReasonType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Appeal reason type classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>

## IntroductionSource

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
			<td><b>IntroductionSource</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Introduction source classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>

## OrderedService

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
			<td><b>ServiceType</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Service type classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>

## RegionOfActivity

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
			<td><b>Region</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>

## CountryOfActivity

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
			<td><b>Country</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
		</tr>
	</tbody>
</table>


## PaymentCountry

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
			<td><b>Country</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>TAXES</td>
			<td>Type of income source code.</td>
	    </tr>
	    <tr>
			<td><b>TurnoverDirection</b></td>
			<td>String<br/><b>ENUM</b><br/> [IN,<br/>OUT]</td>
			<td>true</td>
			<td>OUT</td>
			<td>The turnover direction of payment</td>
	    </tr>
	</tbody>
</table>


## FieldOfActivity

<table>
	<thead>
		<tr>
			<td><b>Field</b></td>
			<td><b>Type</b></td>
			<td><b>Mandatory</b></td>
			<td><b>Reference</b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b>Employment</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#Employment">Employment</a></td>
		</tr>
		<tr>
			<td><b>Other</b></td>
			<td>Object</td>
			<td>false</td>
			<td><a href="#Other">Other</a></td>
		</tr>
		<tr>
			<td><b>Pension</b></td>
			<td>Object</td>
			<td>false</td>
			<td><a href="#Pension">Pension</a></td>
		</tr>
		<tr>
			<td><b>Student</b></td>
			<td>Object</td>
			<td>false</td>
			<td><a href="#Student">Student</a></td>
		</tr>
	</tbody>
</table>

## Employment

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
			<td><b>EmployerTitle</b></td>
			<td>String</td>
			<td>false</td>
			<td>CompanyB</td>
			<td>Title of the individual employer.</td>
		</tr>
		<tr>
			<td><b>EmploymentPositionDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Software Engineer</td>
			<td>Description of the individual employment position.</td>
		</tr>
		<tr>
			<td><b>IsEmployee</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the individual entity being an employee</td>
		</tr>
		<tr>
			<td><b>IsSelfEmployed</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the individual entity being self-employed</td>
		</tr>
		<tr>
			<td><b>IsUnemployed</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the individual entity being unemployed</td>
		</tr>
	</tbody>
</table>



## Other

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
			<td><b>IsOtherStatus</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for other status individual</td>
	    </tr>
	    <tr>
			<td><b>OtherStatusDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>consultation</td>
			<td>Description of other status</td>
	    </tr>
	</tbody>
</table>


## Pension

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
			<td><b>IsPensioner</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for the individual entity being a pensioner</td>
	    </tr>
	    <tr>
			<td><b>PensionCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>The country is responsible for paying an individual's pension</td>
	    </tr>
	</tbody>
</table>


## Student

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
			<td><b>HigherSchoolCountry</b></td>
			<td>String</td>
			<td>false</td>
			<td>LT</td>
			<td>Indicator for individual entity being a student</td>
	    </tr>
	    <tr>
			<td><b>HigherSchoolTitle</b></td>
			<td>String</td>
			<td>false</td>
			<td>Vilniaus Universitetas MIF</td>
			<td>Title of higher school of the student</td>
	    </tr>
	    <tr>
			<td><b>IsStudent</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Country of higher school of the student</td>
	    </tr>
	</tbody>
</table>

## Activity

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
			<td><b>ActivityType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Activity type classifier)</a>
            </td>
			<td>true</td>
			<td>ACTIVITY_OTHER</td>
			<td>Type of business activity.</td>
	    </tr>
	    <tr>
			<td><b>IncomePercentage</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>15</td>
			<td>Percentage of income from certain activity</td>
	    </tr>
	</tbody>
</table>


## AdditionalValue

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
			<td><b>Code</b></td>
			<td>String</td>
			<td>true</td>
			<td>related_to_usa</td>
			<td>Identifier for additional field</td>
	    </tr>
	    <tr>
			<td><b>Datatype</b></td>
			<td>String<br/><b>ENUM</b><br/>[STRING,<br/> INTEGER,<br/> DECIMAL,<br/> DATE,<br/> TIMESTAMP,<br/> BOOLEAN]</td>
			<td>true</td>
			<td>STRING</td>
			<td>Type of provided value</td>
	    </tr>
	    <tr>
			<td><b>Description</b></td>
			<td>String</td>
			<td>true</td>
			<td>entity has relation to USA</td>
			<td>human readable description of field</td>
	    </tr>
	    <tr>
			<td><b>Value</b></td>
			<td>String</td>
			<td>true</td>
			<td>true</td>
			<td>value of field</td>
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
			<td><b>Example/Ref</b></td>
			<td><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
	    <tr>
			<td><b>AddressDetails</b></td>
			<td>String</td>
			<td>true</td>
			<td>Verkiu 1, Vilnius</td>
			<td>Full address description</td>
	    </tr>
	    <tr>
			<td><b>AddressType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Address type classifier)</a>
            </td>
			<td>false</td>
			<td>RESIDENCE</td>
			<td>Type of entity address.</td>
	    </tr>
	    <tr>
			<td><b>City</b></td>
			<td>String</td>
			<td>false</td>
			<td>Vilnius</td>
			<td>City of given address</td>
	    </tr>
	    <tr>
			<td><b>Country</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country type classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of given address.</td>
	    </tr>
	    <tr>
			<td><b>Region</b></td>
			<td>String</td>
			<td>false</td>
			<td>EU</td>
			<td>Region of given address</td>
	    </tr>
	    <tr>
			<td><b>StreetAddress</b></td>
			<td>String</td>
			<td>false</td>
			<td>Verkiu 1</td>
			<td>Street, house and flat of given address</td>
	    </tr>
	    <tr>
			<td><b>UseForCorrespondence</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Check for using the address in correspondence</td>
	    </tr>
	    <tr>
			<td><b>ZipCode</b></td>
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
			<td><b>Example/Ref</b></td>
			<td><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
	    <tr>
			<td><b>Description</b></td>
			<td>String</td>
			<td>false</td>
			<td>passport</td>
			<td>Document description</td>
	    </tr>
	    <tr>
			<td><b>DocumentExpiryDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2032-01-15</td>
			<td>The expiry date of the document in question</td>
	    </tr>
	    <tr>
			<td><b>DocumentIssueAuthority</b></td>
			<td>String</td>
			<td>true</td>
			<td>migration office</td>
			<td>An authority that issued the document.</td>
	    </tr>
	    <tr>
			<td><b>DocumentIssueCountry</b></td>
			<td>String</td>
			<td>true</td>
			<td>LT</td>
			<td>A country that issued the document</td>
	    </tr>
	    <tr>
			<td><b>DocumentIssueDate</b></td>
			<td>Date</td>
			<td>true</td>
			<td>2022-01-15</td>
			<td>Issue date of the document in question</td>
	    </tr>
	    <tr>
			<td><b>DocumentNumber</b></td>
			<td>String</td>
			<td>true</td>
			<td>0123456789</td>
			<td>Number of document in question</td>
	    </tr>
	    <tr>
			<td><b>EntityType</b></td>
			<td>String<br/><b>ENUM</b><br/> [INDIVIDUAL, <br/> ORGANIZATION]</td>
			<td>true</td>
			<td>INDIVIDUAL</td>
			<td>Entity type describes client status</td>
	    </tr>
	    <tr>
			<td><b>IdentityDocumentType</b></td>
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
			<td><b>Example/Ref</b></td>
			<td><b>Description</b></td>
		</tr>
	</thead>
	<tbody>
	    <tr>
			<td><b>ContactType</b></td>
            <td>String<br/><b>ENUM</b><br/>[MOBILEPHONE, <br/>FIXEDPHONE, <br/>EMAIL,WEBSITE]</td>
			<td>true</td>
			<td>MOBILEPHONE</td>
			<td>Way of contacting entity.</td>
	    </tr>
	    <tr>
			<td><b>ContactDetails</b></td>
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
			<td><b>UseForCommunication</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true/false</td>
			<td>Indicator for the usage of communication way.</td>
	    </tr>
	</tbody>
</table>


## CountryOfTaxPayment

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
			<td><b>Country</b></td>
            <td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of tax payment</td>
	    </tr>
	    <tr>
			<td><b>TaxpayerNumber</b></td>
			<td>String</td>
			<td>false</td>
			<td>5541245574</td>
			<td>The number of tax payer</td>
	    </tr>
	</tbody>
</table>

## DeclaredTurnover

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
			<td><b>From</b></td>
			<td>BigInteger</td>
			<td>true/false</td>
			<td>1000</td>
			<td>Amount range from. At least one value (From or To) must be specified</td>
	    </tr>
	    <tr>
			<td><b>To</b></td>
			<td>String</td>
			<td>true/false</td>
			<td>5000</td>
			<td>Amount to. At least one value (From or To) must be specified</td>
	    </tr>
	    <tr>
			<td><b>TurnoverRange</b></td>
			<td>String<br/><b>ENUM</b><br/> [SINGLE,<br/> DAILY, <br/> MONTHLY,<br/> ANNUAL]</td>
			<td>true</td>
			<td>MONTHLY</td>
			<td>Range of declared turnover</td>
	    </tr>
	    <tr>
			<td><b>TurnoverType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Turnover type classifier)</a>
            </td>
			<td>true</td>
			<td>TURNOVER_PER_MONTH</td>
			<td>Type of declared turnover</td>
	    </tr>
	</tbody>
</table>

## IncomeSource

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
			<td><b>From</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>100</td>
			<td>Amount from</td>
	    </tr>
	    <tr>
			<td><b>IncomePercentage</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>5</td>
			<td>Percentage of income from the source</td>
	    </tr>
	    <tr>
			<td><b>IncomeSourceType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Income source type classifier)</a>
            </td>
			<td>true</td>
			<td>SALARY</td>
			<td>Type of income source</td>
	    </tr>
	    <tr>
			<td><b>To</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>1000</td>
			<td>Amount to</td>
	    </tr>
	</tbody>
</table>


## PaymentPurpose

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
			<td><b>PaymentPurposeType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Payment purpose type classifier)</a>
            </td>
			<td>true</td>
			<td>TAXES</td>
			<td>Type of income source code.</td>
	    </tr>
	    <tr>
			<td><b>TurnoverDirection</b></td>
			<td>String<br/><b>ENUM</b><br/> [IN,<br/>OUT]</td>
			<td>true</td>
			<td>OUT</td>
			<td>The turnover direction of payment</td>
	    </tr>
	</tbody>
</table>

## SourceOfWealth

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
			<td><b>Value</b></td>
			<td>BigDecimal</td>
			<td>false</td>
			<td>100000</td>
			<td>Collected monetary amount</td>
	    </tr>
	    <tr>
			<td><b>SourceOfWealthCode</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Source of wealth type classifier)</a>
            </td>
			<td>true</td>
			<td>INHERITANCE</td>
			<td>source of wealth code</td>
	    </tr>
	    <tr>
			<td><b>Comment</b></td>
			<td>String</td>
			<td>false</td>
			<td>Wealth received from Inheritance</td>
			<td>Additional details about the source of wealth</td>
	    </tr>
	</tbody>
</table>                 

## RelatedEntity

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
			<td><b>RelationType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Relation type classifier)</a>
            </td>
			<td>true</td>
			<td>OWNER</td>
			<td>Type of relationship between entities.</td>
	    </tr>
	    <tr>
			<td><b>Share</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>75</td>
			<td>Shares owned by shareholders in the organization of the business entity</td>
	    </tr>
	    <tr>
			<td><b>VotePercentage</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>99</td>
			<td>Vote percentage of shareholders in the organization of business entity</td>
	    </tr>
	    <tr>
			<td><b>ActivityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>financial activity</td>
			<td>Activity description of the related entity</td>
	    </tr>
	    <tr>
			<td><b>BirthCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>The birth country of the related entity</td>
	    </tr>
	    <tr>
			<td><b>BirthDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2000-05-28</td>
			<td>Birth date of a related individual entity</td>
	    </tr>
	    <tr>
			<td><b>Country</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of the related entity</td>
	    </tr>
	    <tr>
			<td><b>EntityType</b></td>
			<td>String<br/><b>ENUM</b><br/> [INDIVIDUAL, <br/>ORGANIZATION]</td>
			<td>true</td>
			<td>INDIVIDUAL</td>
			<td>Entity type describes client status</td>
	    </tr>
	    <tr>
			<td><b>EstablishmentDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2020-05-30</td>
			<td>Establishment date of related organization entity</td>
	    </tr>
	    <tr>
			<td><b>ExtId</b></td>
			<td>String</td>
			<td>false</td>
			<td>12345678912345</td>
			<td>Used for screening callbacks to identify entity</td>
	    </tr>
	    <tr>
			<td><b>FirstName</b></td>
			<td>String</td>
			<td>true/false</td>
			<td>John</td>
			<td>First name of related entity br><b>Mandatory</b> when entityType = INDIVIDUAL <br/><b>Not Used</b>  when entityType = ORGANIZATION</td>
	    </tr>
	    <tr>
			<td><b>IsInAdverseMedia</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>An indication of the existence of information for an adverse media entity</td>
	    </tr>
	    <tr>
			<td><b>IsPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>An indicator for a related individual entity is a politically exposed person</td>
	    </tr>
	    <tr>
			<td><b>IsSanctioned</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for sanctions applied to the entity</td>
	    </tr>
	    <tr>
			<td><b>LastName</b></td>
			<td>String</td>
			<td>true/false</td>
			<td>Rodriguez</td>
			<td>Last name of related entity <br/><b>Mandatory</b> when entityType = INDIVIDUAL <br/><b>Not Used</b>  when entityType = ORGANIZATION</td>
	    </tr>
	    <tr>
			<td><b>LegalForm</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Legal form classifier)</a>
            </td>
			<td>false</td>
			<td>COOPERATIVE</td>
			<td>Legal form of organization</td>
	    </tr>
	    <tr>
			<td><b>NationalCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>123456789</td>
			<td>National code or national identification number of individual or organization. If a country does not issue national code, any other unique identifier can be used</td>
	    </tr>
	    <tr>
			<td><b>RegionOfActivityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>EU</td>
			<td>Description of activity region of related entity</td>
	    </tr>
	    <tr>
			<td><b>RegistrationCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of registration of related entity</td>
	    </tr>
	    <tr>
			<td><b>RelationDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>founder</td>
			<td>Description of the relationship between entities</td>
	    </tr>
	    <tr>
			<td><b>Title</b></td>
			<td>String</td>
			<td>true/ false</td>
			<td>Beko</td>
			<td><br/><b>Mandatory</b> when entityType = ORGANIZATION <br/><b>Not Used</b>  when entityType = INDIVIDUAL</td>
	    </tr>
	    <tr>
			<td><b>ListActivity</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#Activity">Activity[]</a></td>
			<td>List of activities of related entity</td>
    	</tr>
    	<tr>
			<td><b>ListAdditionalValues</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#AdditionalValue">AdditionalValue[]</a></td>
			<td>Additional information about businessEntity</td>
    	</tr>
    	<tr>
			<td><b>ListAddress</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#Address">Address[]</a></td>
			<td>List of addresses</td>
    	</tr>
    	<tr>
			<td><b>ListBusinessEntityDocument</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#BusinessEntityDocument">BusinessEntityDocument[]</a></td>
			<td>List of related entity document</td>
    	</tr>
    	<tr>
			<td><b>ListContact</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#Contact">Contact[]</a></td>
			<td>List of contacts of related entity</td>
    	</tr>
    	<tr>
			<td><b>ListCountryOfActivity</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#CountryOfActivity">CountryOfActivity[]</a></td>
			<td>List of activity countries of related entity</td>
	    </tr>
	    <tr>
			<td><b>ListIncomeSource</b></td>
			<td>Object</td>
			<td>false</td>
			<td><a href="#IncomeSource">IncomeSource[]</a></td>
			<td>List of income sources</td>
	    </tr>
	    <tr>
			<td><b>ListRegionOfActivity</b></td>
			<td>Object</td>
			<td>false</td>
            <td><a href="#RegionOfActivity">RegionOfActivity[]</a></td>
			<td>List of activity regions of related entity</td>
	    </tr>
	</tbody>
</table>
