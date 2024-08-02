# ORGANIZATION Fields

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
			<td>Test_ComNr_003ZZZD</td>
			<td>Unique number of communication. used for risk assessment callback. This field can store up to 256 characters</td>
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
			<td>Element is used to change the data of an existing Customer. <br/>❗ NOTE: all data will be replaced with newly received ones</td>
		</tr>
		<tr>
			<td><b>sourceOfRiskLevel</b></td>
			<td>String<br/><b>ENUM</b><br/>[IMPORT,EVALUATE]</td>
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
			<td>Customer's predefined status represents the current standing or state of a customer's relationship with a business or organization <br/> <i> PENDING - Customer application is received but not yet prepared for upcoming workflow <br/> ACTIVE - Customer is onboarded and ready for workflow <br/> REJECTED - the customer for some reasons was rejected before opening an account for him. <br/>SUSPENDED - Customer's activities for some reasons are restricted <br/> CLOSED - Customer's profile is disabled</i><br/> <b>Mandatory</b> when sourceOfRiskLevel = IMPORT<br/> <b>Not Used</b>  when sourceOfRiskLevel = EVALUATE</td>
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
            ❗<b>Omit this parameter unless instructed about it.</b>❗<br/> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data. Each business unit can have its own set of users, permissions, and data access rules. <br/><i>(Upcoming feature)</i></td>
		</tr>
		<tr>
			<td><b>riskManagementCategory</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Risk management category classifier)</a>
            </td>
			<td>true</td>
			<td>ORG</td>
			<td>
                Code of risk management category for evaluation of the object.<br/>💡 
                Possible values here are given just as an example, in the configuration period these could be updated
            </td>
		</tr>
		<tr>
			<td><b>entityType</b></td>
			<td>String<br/><b>ENUM</b><br/>[ORGANIZATION]</td>
			<td>true</td>
			<td>ORGANIZATION</td>
			<td>Type of business entity</td>
		</tr>
		<tr>
			<td><b>customerExtId</b></td>
			<td>String</td>
			<td>true</td>
			<td>ORG_C1_TEST</td>
			<td>Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution</td>
		</tr>
		<tr>
			<td><b>applicationDate</b></td>
			<td>Date</td>
			<td>true</td>
			<td>2000-01-03</td>
			<td>Date when customer first applied</td>
		</tr>
		<tr>
			<td><b>title</b></td>
			<td>String</td>
			<td>true</td>
			<td>LTD 'MinorMajor'</td>
			<td>Title of organization entity</td>
		</tr>
		<tr>
			<td><b>registrationCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of registration of the organization</td>
		</tr>
		<tr>
			<td><b>legalForm</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Legal form classifier)</a>
            </td>
			<td>true</td>
			<td>LTD</td>
			<td>Legal form of organization</td>
		</tr>
		<tr>
			<td><b>tradingName</b></td>
			<td>String</td>
			<td>false</td>
			<td>MinorMajor</td>
			<td>Trading name of organization</td>
		</tr>
		<tr>
			<td><b>approvalDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2020-01-05</td>
			<td>Date of application approval</td>
		</tr>
		<tr>
			<td><b>establishmentDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2001-02-23</td>
			<td>Establishment date for organization type entities</td>
		</tr>
		<tr>
			<td><b>closingDate</b></td>
			<td>Date</td>
			<td>true/false</td>
			<td>1995-05-24</td>
			<td>Date of closure of all accounts <br/><b>Mandatory</b> when customerStatus = CLOSED<br/><b>Not Mandatory</b>  when customerStatus = PENDING, ACTIVE, REJECTED, SUSPENDED</td>
		</tr>
		<tr>
			<td><b>nationalCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>REG74121101</td>
			<td>National code or national identification number of organization. If a country does not issue national code, any other unique identifier can be used:<br/> <i>* Passport number;<br/>* Social security number of person; <br/> * A number of taxpayer or registration certificate of the company, etc <br/> * A number of taxpayer or registration certificate of the company</i></td>
		</tr>
		<tr>
			<td><b>activityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Logistics</td>
			<td>Description of entity activity</td>
		</tr>
		<tr>
			<td><b>activityInRestrictedRegionDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Logistics</td>
			<td>Description of business entities' activities in a restricted region</td>
		</tr>
		 <tr>
			<td><b>isPEP</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>An indicator that an entity inside the organization is a politically exposed person</td>
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
			<td><b>giin</b></td>
			<td>String</td>
			<td>false</td>
			<td>GIN548745122</td>
			<td>Global intermediary identification number.</td>
		</tr>
		<tr>
			<td><b>lei</b></td>
			<td>String</td>
			<td>false</td>
			<td>LEI54511548</td>
			<td>LEI stands for Legal Entity Identifier, which is a unique code used to identify legal entities that participate in financial transactions</td>
		</tr>
		<tr>
			<td><b>listPurpose</b></td>
			<td>String<br/><b>ENUM</b><br/>[BLACK,<br/> WHITE]</td>
			<td>false</td>
			<td>BLACK</td>
			<td>Whether entity is black/white listed</td>
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
			<td>Indicator for correspondence address declaration</td>
		</tr>
		 <tr>
			<td><b>incomeSourceDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Salary</td>
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
			<td><b>isAudited</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the business entity being audited</td>
		</tr>
		<tr>
			<td><b>numberOfAudits</b></td>
			<td>Integer</td>
			<td>false</td>
			<td>6</td>
			<td>The number of times a business entity has been audited</td>
		</tr>
		<tr>
			<td><b>periodsOfAuditsInYears</b></td>
			<td>integer</td>
			<td>false</td>
			<td>3</td>
			<td>The number of years that are in question for being audited</td>
		</tr>
		<tr>
			<td><b>organizationalStructureDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Hierarchical</td>
			<td>Description of organization structure</td>
		</tr>
		<tr>
			<td><b>hasMultiLayerStructure</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Check for multi-layer organizational structure</td>
		</tr>
		<tr>
			<td><b>isFinancialInstitution</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Whether entity is financial institution</td>
		</tr>
		<tr>
			<td><b>isDirectlyManaged</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Check for direct management</td>
		</tr>
  		<tr>
			<td><b>noMajorShareHolders</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Check for no major shareholders involved</td>
		</tr>
		<tr>
			<td><b>numberOfEmployees</b></td>
			<td>Integer</td>
			<td>false</td>
			<td>25</td>
			<td>The number of employees in the company</td>
		</tr>
		<tr>
			<td><b>companyAssetValue</b></td>
			<td>BigInteger</td>
			<td>false</td>
			<td>100000</td>
			<td>value of companies assets</td>
		</tr>
		<tr>
			<td><b>isFined</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Whether entity has fines</td>
		</tr>
		<tr>
			<td><b>periodsOfFiningInYears</b></td>
			<td>integer</td>
			<td>false</td>
			<td>3</td>
			<td>The number of years that are in question for being fined</td>
		</tr>
		<tr>
			<td><b>isListed</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>false</td>
			<td>Indicator for the business entity is listed in stock exchange companies</td>
		</tr>
		<tr>
			<td><b>isRegulated</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Indicator for the business entity being regulated by third-party authorities</td>
		</tr>
        <tr>
			<td><b>isLicenseRequired</b></td>
			<td>Boolean</td>
			<td>false</td>
			<td>true</td>
			<td>Whether entity activity requires license</td>
		</tr>
		<tr>
			<td><b>licenseDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Licence No.4012</td>
			<td>Business entities license description</td>
		</tr>
		<tr>
			<td><b>thirdPartyServicesUsed</b></td>
			<td>String</td>
			<td>false</td>
			<td>true</td>
			<td>Whether client is using third party services</td>
		</tr>
		<tr>
			<td><b>thirdPartyServicesUsedDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Hosting</td>
			<td>Description of third party services</td>
		</tr>
        <tr>
			<td><b>regionOfActivityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Customer service</td>
			<td>Description of the region for activities</td>
		</tr>
        <tr>
			<td><b>listContact</b></td>
            <td><a href="#ContactApi">ContactApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of contacts of business entity</td>
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
			<td>true</td>
			<td>Verkiu 1, Vilnius</td>
			<td>Full address description</td>
	    </tr>
	    <tr>
			<td><b>addressType</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Address type classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Country type classifier)</a>
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
			<td>ORGANIZATION</td>
			<td>Entity type describes client status</td>
	    </tr>
	    <tr>
			<td><b>identityDocumentType</b></td>
			<td>String<br/><b>ENUM</b><br/>[PASSPORT, <br/> IDENTITYCARD,<br/> RESIDENCEPERMIT,<br/> DRIVINGLICENSE,<br/> REGISTRATIONCERTIFICATE,<br/> OTHER]</td>
			<td>true</td>
			<td>REGISTRATIONCERTIFICATE</td>
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
                <a href="../../../Classifiers/classifiers.md">(Appeal reason type classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Introduction source classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Service type classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Turnover type classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Income source type classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Payment purpose type classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Source of wealth type classifier)</a>
            </td>
			<td>true</td>
			<td>INHERITANCE</td>
			<td>source of wealth code</td>
	    </tr>
	    <tr>
			<td><b>comment</b></td>
			<td>String</td>
			<td>false</td>
			<td></td>
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
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Activity type classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
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
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
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
			<td>relation_usa</td>
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
			<td>entity has relation to USA</td>
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



## RelatedEntityApi

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
                <a href="../../../Classifiers/classifiers.md">(Relation type classifier)</a>
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
			<td>Rel_entity_ExtID_4052</td>
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
			<td><b>activityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Financial activity</td>
			<td>Activity description of the related entity</td>
	    </tr>
		<tr>
			<td><b>regionOfActivityDescription</b></td>
			<td>String</td>
			<td>false</td>
			<td>Central Europe</td>
			<td>Description of activity region of related entity</td>
	    </tr>
		<tr>
			<td><b>nationalCode</b></td>
			<td>String</td>
			<td>false</td>
			<td>123456789</td>
			<td>National code or national identification number of individual or organization. If a country does not issue national code, any other unique identifier can be used</td>
	    </tr>
	    <tr>
			<td><b>birthCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>The birth country of the related entity</td>
	    </tr>
	    <tr>
			<td><b>birthDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2000-05-28</td>
			<td>Birth date of a related individual entity</td>
	    </tr>
	    <tr>
			<td><b>country</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>false</td>
			<td>LT</td>
			<td>Country of the related entity</td>
	    </tr>
		<tr>
			<td><b>registrationCountry</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Country classifier)</a>
            </td>
			<td>true</td>
			<td>LT</td>
			<td>Country of registration of the related organization</td>
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
			<td><b>firstName</b></td>
			<td>String</td>
			<td>true/false</td>e
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
			<td><b>title</b></td>
			<td>String</td>
			<td>true/ false</td>
			<td>LTD 'Fokusmano'</td>
			<td><br/><b>Mandatory</b> when entityType = ORGANIZATION <br/><b>Not Used</b>  when entityType = INDIVIDUAL</td>
	    </tr>
	    <tr>
			<td><b>legalForm</b></td>
			<td>
                String <br/>
                <a href="../../../Classifiers/classifiers.md">(Legal form classifier)</a>
            </td>
			<td>false</td>
			<td>COOPERATIVE</td>
			<td>Legal form of organization</td>
	    </tr>
		<tr>
			<td><b>establishmentDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>1998-04-07</td>
			<td>Establishment date of related organization entity</td>
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
			<td><b>listCountryOfActivity</b></td>
            <td><a href="#CountryOfActivityApi">CountryOfActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activity countries of related entity</td>
	    </tr>
	    <tr>
			<td><b>listRegionOfActivity</b></td>
            <td><a href="#RegionOfActivityApi">RegionOfActivityApi[]</a></td>
			<td>false</td>
			<td>-</td>
			<td>List of activity regions of related entity</td>
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
