# INDIVIDUAL Fields 

<table>
	<thead>
		<tr>
			<td><b> field </td>
			<td><b> type </td>
			<td><b> mandatory </td>
			<td><b> example </td>
			<td  width:600px><b> description </td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b> communicationNumber </td>
			<td> String </td>
			<td><b> true </td>
			<td> ComNr_000321 </td>
			<td> Unique number of communication. used for risk assessment callback </td>
		</tr>
		<tr>
			<td><b> requester  </td>
			<td> String </td>
			<td><b> true </td>
			<td>ComNr_000321 </td>
			<td> Name of the system requesting web service </td>
		</tr>
		<tr>
			<td><b> action </td>
			<td> <b>ENUM</b> <br/>[CREATE (<i>default</i>), <br/> UPDATE] </td>
			<td> false </td>
			<td> UPDATE </td>
			<td> Element is used to change the data of an existing Customer. </br>❗ NOTE: all data will be replaced with newly received ones </td>
		</tr>
		<tr>
			<td><b>riskManagementCategory </td>
			<td> String <br>(classifier) </td>
			<td><b> true </td>
			<td>IND_PK</td>
			<td>Code of risk management category for evaluation of the object.<br>💡 Possible values here are given just as an example, in the configuration period these could be updated</td>
		</tr>
		<tr>
			<td><b>sourceOfRiskLevel </td>
			<td> <b>ENUM</b><br>[IMPORT,EVALUATE] </td>
			<td><b> true </td>
			<td>IMPORT </td>
			<td>Source of risk level<br> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed. </br> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment</td>
		</tr>
		<tr>
			<td><b> riskLevel </td>
			<td> <b>ENUM</b></br>[NONE,</br> LOW,</br> MEDIUM,</br> HIGH,</br> EXTREME]  </td>
			<td> true/false </b> </td>
			<td> HIGH </td>
			<td>The Risk Level of the customer during IMPORT</br><b>Mandatory</b> when sourceOfRiskLevel = IMPORT</br>
<b>Not Mandatory</b>  when sourceOfRiskLevel = EVALUATE</td>
		</tr>
		<tr>
			<td><b> initializeScreeningProcesses </td>
			<td> String </td>
			<td> false </td>
			<td> SANCTIONS,<br>
PEP,</br> ADVERSE_MEDIA </td>
			<td>Defines which screening processes to initiate</td>
		</tr>
		<tr>
			<td><b>customerStatus</td>
			<td> <b>ENUM</b></br>[PENDING,</br>ACTIVE,</br> REJECTED,</br> SUSPENDED,</br>CLOSED] </td>
			<td><b> true </td>
			<td> ACTIVE</td>
			<td> Customer status represents the current standing or state of a customer's relationship with a business or organization </br> <i> PENDING - Customer application is received.</br> ACTIVE - Customer is onboarded ( account is provided or customer assessment case is resolved)</br> REJECTED - the customer for some reasons was rejected before opening an account for him. </br>SUSPENDED - Customer's activities for some reasons are restricted </br> CLOSED - Customer's profile is changed to being disabled </td>
		</tr>
		<tr>
			<td><b> customerExtId </td>
			<td> String </td>
			<td><b> true </td>
			<td> cust_1232</td>
			<td>Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution </td>
		</tr>
		<tr>
			<td><b> entityType </td>
			<td> <b>ENUM</b></br>[INDIVIDUAL] </td>
			<td><b> true </td>
			<td> INDIVIDUAL </td>
			<td> Whether bussines or individual entity </td>
		</tr>
		<tr>
			<td><b> nationalCode </td>
			<td> String </td>
			<td> false </td>
			<td> REG74121101 </td>
			<td>National code or national identification number of individual. If a country does not issue national code, any other unique identifier can be used:</br> <i>* Passport number;</br>* Social security number of person; </br> * A number of taxpayer or registration certificate of the company, etc </br> * A number of taxpayer or registration certificate of the company</td>
		</tr>
		<tr>
			<td><b> applicationDate </td>
			<td> Date </td>
			<td><b> true </td>
			<td> 2000-01-03 </td>
			<td>Date when customer first applied</td>
		</tr>
		<tr>
			<td><b> activityDescription </td>
			<td> String </td>
			<td>false </td>
			<td> financial activity </td>
			<td>Description of entity activity</td>
		</tr>
		<tr>
			<td><b>activityInRestrictedRegionDescription</td>
			<td> String </td>
			<td> false  </td>
			<td> logistics </td>
			<td> Description of business entities' activities in a restricted region </td>
		</tr>
		<tr>
			<td><b>amlOfficer</td>
			<td>Boolean </td>
			<td><b> false </td>
			<td> false </td>
			<td> Indicator for the person being AML officer </td>
		</tr>
		<tr>
			<td><b> approvalDate </td>
			<td> Date  </td>
			<td>false  </td>
			<td> 2000-01-03  </td>
			<td> Date of application approval </td>
		</tr>
		<tr>
			<td><b> birthCountry  </td>
			<td>String </td>
			<td> <b>true  </td>
			<td> LT </td>
			<td> Country of birth of individual entity </td>
		</tr>
		<tr>
			<td><b> birthDate   </td>
			<td> Date  </td>
			<td> <b>true  </td>
			<td> 1995-05-24  </td>
			<td> Date of birth of individual entity</td>
		</tr>
		<tr>
			<td><b> citizenshipCountry  </td>
			<td> String </td>
			<td><b> true </td>
			<td> LT  </td>
			<td> Country of citizenship of individual entity </td>
		</tr>
		<tr>
			<td><b> closingDate  </td>
			<td>Date  </td>
			<td> true/false  </td>
			<td> 1995-05-24  </td>
			<td> Date of closure of all accounts </br><b>Mandatory</b> when customerStatus = CLOSED</br><b>Not Mandatory</b>  when customerStatus = PENDING, ACTIVE, REJECTED, SUSPENDED </td>
		</tr>
        <tr>
			<td><b> doesCashDominate </td>
			<td> Boolean  </td>
			<td> false  </td>
			<td> true   </td>
			<td> Indicator for cash being the main income source </td>
		</tr>
        <tr>
			<td><b> firstName </td>
			<td> String </td>
			<td> <b>true </td>
			<td> Jose  </td>
			<td> First name of individual entity </td>
		</tr>
        <tr>
			<td ><b> lastName  </td>
			<td > String </td>
			<td > <b>true </td>
			<td > Rodriguez </td>
			<td> Last name of individual entity  </td>
		</tr>
        <tr>
			<td><b> incomeSourceDescription </td>
			<td> String </td>
			<td>false </td>
			<td> work </td>
			<td> Description of income source of the entity </td>
		</tr>
		<tr>
			<td><b> incomingPaymentDescription </td>
			<td> String </td>
			<td> false </td>
			<td> payment for work </td>
			<td> Description of incoming payment operation </td>
		</tr>
		<tr>
			<td><b> initialDepositAccount </td>
			<td> String </td>
			<td> false </td>
			<td> LT0000000000000000 </td>
			<td> Account of initial deposit </td>
		</tr>
		<tr>
			<td><b> initialDepositAmount  </td>
			<td> Double  </td>
			<td> false </td>
			<td> 10000 </td>
			<td> Amount of initial deposit </td>
		</tr>
		<tr>
			<td><b> initialDepositBank  </td>
			<td> String </td>
			<td> false </td>
			<td> BankBank  </td>
			<td> Bank of the initial deposit </td>
		</tr>
		<tr>
			<td><b> initialDepositCurrency  </td>
			<td> String </td>
			<td> false </td>
			<td> EUR  </td>
			<td> Currency field notifies about the currency used in a certain operation. </td>
		</tr>
		<tr>
			<td ><b> initialDepositSource  </td>
			<td> String </td>
			<td> false </td>
			<td> Dividend  </td>
			<td> Source of initial deposit </td>
		</tr>
		<tr>
			<td><b> isActualAddressDeclared </td>
			<td> Boolean  </td>
			<td> false </td>
			<td> false  </td>
			<td> Whether customer declared ActualAddress  </td>
		</tr>
        <tr>
			<td><b> isFamilyPEP  </td>
			<td> Boolean </td>
			<td> false </td>
			<td> false </td>
			<td> Identification of whether or not a family member of an Individual entity is politically exposed </td>
		</tr>
        <tr>
			<td><b> isInAdverseMedia  </td>
			<td> Boolean </td>
			<td> false </td>
			<td> true </td>
			<td> An indication of the existence of information for an adverse media entity </td>
		</tr>
		<tr>
			<td><b> isLegalResident  </td>
			<td> Boolean  </td>
			<td> false </td>
			<td > true </td>
			<td> Indicator for whether or not the individual entity is a legal resident </td>
		</tr>
        <tr>
			<td ><b> isLitigated  </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> Indicator for the person being litigated </td>
		</tr>
		<tr>
			<td ><b> isPEP  </td>
			<td > Boolean  </td>
			<td > false </td>
			<td > false </td>
			<td> Identification for whether or not a person is politically exposed </td>
		</tr>
        <tr>
			<td ><b> isSanctioned  </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Whether entity is sanctioned  </td>
		</tr>
        <tr>
			<td ><b> permanentResidenceCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of permanent residency of an individual entity </td>
		</tr>
        <tr>
			<td ><b> secondCitizenshipCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of second citizenship of individual entity </td>
		</tr>
        <tr>
			<td ><b> listPurpose </td>
			<td > ENUM <br/><b>[BLACK,<br/> WHITE] </td>
			<td > false </td>
			<td > - </td>
			<td> Whether entity is black/white listed </td>
		</tr>
		<tr>
			<td ><b> fieldOfActivity </td>
			<td > FieldOfActivityApi </td>
			<td > false </td>
			<td > - </td>
			<td> Information about the activities </td>
		</tr>
		<tr>
			<td ><b> listActivity </td>
			<td > [ActivityApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activities </td>
		</tr>
		<tr>
			<td ><b> listAdditionalValues </td>
			<td > [AdditionalValueApi] </td>
			<td > false </td>
			<td > - </td>
			<td> Additional information about businessEntity </td>
		</tr>
		<tr>
			<td ><b> listAddress </td>
			<td > [AddressApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of addresses </td>
		</tr>
		<tr>
			<td ><b> listAppealReason </td>
			<td > [AppealReasonType] </td>
			<td > false </td>
			<td > - </td>
			<td> List of reasons for the appeal </td>
		</tr>
		<tr>
			<td ><b> listBusinessEntityDocument </td>
			<td > [BusinessEntityDocumentApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of related entity documents </td>
		</tr>
		<tr>
			<td ><b> listContact </td>
			<td > [ContactApi] </td>
			<td > false </td>
			<td> - </td>
			<td> List of contacts of related entity </td>
		</tr>
		<tr>
			<td ><b> listCountryOfActivity </td>
			<td > [countryOfActivity] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activity regions </td>
		</tr>
		<tr>
			<td ><b> listCountryOfTaxPayment </td>
			<td > [CountryOfTaxPaymentApi] </td>
			<td> false </td>
			<td > - </td>
			<td> List of tax payment country </td>
		</tr>
		<tr>
			<td ><b> listDeclaredTurnover </td>
			<td > [DeclaredTurnoverApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of declared turnover </td>
		</tr>
		<tr>
			<td ><b> listIncomeSource </td>
			<td > [IncomeSourceApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of countries of payment </td>
		</tr>
		<tr>
			<td ><b> listIntroductionSource </td>
			<td > [IntroductionSource] </td>
			<td > false </td>
			<td > - </td>
			<td> List of sources of introduction </td>
		</tr>
		<tr>
			<td ><b> listOrderedService </td>
			<td > [serviceType] </td>
			<td > false </td>
			<td > - </td>
			<td> List of ordered services </td>
		</tr>
		<tr>
			<td ><b> listPaymentCountry </td>
			<td > [country] </td>
			<td > false </td>
			<td > - </td>
			<td> List of payment country </td>
		</tr>
		<tr>
			<td ><b> listPaymentPurpose </td>
			<td > [PaymentPurposeApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of payment purpose </td>
		</tr>
		<tr>
			<td ><b> listRegionOfActivity </td>
			<td > [regionOfActivity] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activity countries of related entity </td>
		</tr>
		<tr>
			<td ><b> listSourceOfWealth </td>
			<td > [SourceOfWealthApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of wealth sources </td>
		</tr>
		<tr>
			<td ><b> listRelatedEntity </td>
			<td > [RelatedEntityApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List for related business entities </td>
		</tr>
	</tbody>
</table>

## FieldOfActivityApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td > <b> employment </td>
			<td > FieldEmploymentApi </td>
			<td > false </td>
		</tr>
		<tr>
			<td > <b> other </td>
			<td > FieldOtherApi </td>
			<td > false </td>
		</tr>
		<tr>
			<td > <b> pension </td>
			<td > FieldPensionApi </td>
			<td > false </td>
		</tr>
		<tr>
			<td > <b> student </td>
			<td > FieldStudentApi </td>
			<td > false </td>
		</tr>
	</tbody>
</table>

**FieldEmploymentApi**

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td ><b> employerTitle </td>
			<td > String </td>
			<td > false </td>
			<td > CompanyB  </td>
			<td> Title of the individual employer. </td>
		</tr>
		<tr>
			<td ><b> employmentPositionDescription </td>
			<td > String </td>
			<td > false </td>
			<td > Software Engineer  </td>
			<td> Description of the individual employment position.  </td>
		</tr>
		<tr>
			<td ><b> isEmployee </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false  </td>
			<td> Indicator for the individual entity being an employee </td>
		</tr>
		<tr>
			<td ><b> isSelfEmployed </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false  </td>
			<td> Indicator for the individual entity being self-employed </td>
		</tr>
		<tr>
			<td ><b> isUnemployed </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false  </td>
			<td> Indicator for the individual entity being unemployed </td>
		</tr>
	</tbody>
</table>



**FieldOtherApi**

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> isOtherStatus </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Indicator for other status individual </td>
	</tr>
	<tr>
			<td > <b> otherStatusDescription </td>
			<td > String </td>
			<td > false </td>
			<td > consultation </td>
			<td> Description of other status </td>
	</tr>
	</tbody>
</table>


**FieldPensionApi**

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> isPensioner </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Indicator for the individual entity being a pensioner </td>
	</tr>
	<tr>
			<td > <b> pensionCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> The country is responsible for paying an individual's pension </td>
	</tr>
	</tbody>
</table>


**FieldStudentApi**

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> higherSchoolCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Indicator for individual entity being a studen </td>
	</tr>
	<tr>
			<td > <b> higherSchoolTitle </td>
			<td > String </td>
			<td > false </td>
			<td > Vilniaus Universitetas MIF </td>
			<td> Title of higher school of the student </td>
	</tr>
	<tr>
			<td > <b> isStudent </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Country of higher school of the student </td>
	</tr>
	</tbody>
</table>

## ActivityApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> activityType </td>
			<td > String </td>
			<td > <b> true </td>
			<td > ACTIVITY_OTHER </td>
			<td> Type of business activity. Code from activity classifier </td>
	</tr>
	<tr>
			<td > <b> incomePercentage </td>
			<td > BigInteger </td>
			<td > false </td>
			<td >15  </td>
			<td> Percentage of income from certain activity </td>
	</tr>
	</tbody>
</table>


## AdditionalValueApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> code </td>
			<td > String </td>
			<td ><b> true </td>
			<td > related_to_usa </td>
			<td> Identifier for additional field</td>
	</tr>
	<tr>
			<td > <b> datatype </td>
			<td > <b>ENUM </b></br>[STRING,</br> INTEGER,</br> DECIMAL,</br> DATE,</br> TIMESTAMP,</br> BOOLEAN\] </td>
			<td > <b>true </td>
			<td > STRING </td>
			<td> Type of provided value </td>
	</tr>
	</tbody>
	<tr>
			<td > <b> description </td>
			<td > String </td>
			<td > <b>true </td>
			<td > entity has relation to USA </td>
			<td> human readable description of field </td>
	</tr>
	<tr>
			<td > <b> value </td>
			<td > String </td>
			<td ><b> true </td>
			<td > true </td>
			<td> value of field </td>
	</tr>
	</tbody>
	
</table>


## AddressApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> addressDetails </td>
			<td > String </td>
			<td > <b>true </td>
			<td > Verkiu 1, Vilnius </td>
			<td> Full address description </td>
	</tr>
	<tr>
			<td > <b> addressType </td>
			<td > String </td>
			<td > false </td>
			<td > RESIDENCE </td>
			<td> Type of entity address. Classifier AddressType </td>
	</tr>
	<tr>
			<td > <b> city </td>
			<td > String </td>
			<td > false </td>
			<td > Vilnius </td>
			<td> City of given address </td>
	</tr>
	<tr>
			<td > <b> country </td>
			<td > String </td>
			<td > <b>true </td>
			<td > LT </td>
			<td> Country of given addres. Classifier Country</td>
	</tr>
	<tr>
			<td > <b> region </td>
			<td > String </td>
			<td > false </td>
			<td > EU </td>
			<td> Region of given address </td>
	</tr>
	<tr>
			<td > <b> streetAddress </td>
			<td > String </td>
			<td > false </td>
			<td > Verkiu 1 </td>
			<td> Street, house and flat of given address </td>
	</tr>
	<tr>
			<td > <b> useForCorrespondence </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Check for using the address in correspondence </td>
	</tr>
	<tr>
			<td > <b> zipCode </td>
			<td > String </td>
			<td > false </td>
			<td > 12345 </td>
			<td> Zip code of the address </td>
	</tr>
	</tbody>
</table>


## BusinessEntityDocumentApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> description </td>
			<td > String </td>
			<td > false </td>
			<td > passport </td>
			<td> Document description </td>
	</tr>
	<tr>
			<td > <b> documentExpiryDate </td>
			<td > Date </td>
			<td > false </td>
			<td > 2032-01-15  </td>
			<td> The expiry date of the document in question </td>
	</tr>
	<tr>
			<td > <b> documentIssueAuthority </td>
			<td > String </td>
			<td > <b>true </td>
			<td >migration office  </td>
			<td> An authority that issued the document. </td>
	</tr>
	<tr>
			<td > <b> documentIssueCountry </td>
			<td > String </td>
			<td ><b> true </td>
			<td > LT </td>
			<td> A country that issued the document </td>
	</tr>
	<tr>
			<td > <b> documentIssueDate </td>
			<td > Date </td>
			<td ><b> true </td>
			<td > 2022-01-15  </td>
			<td>Issue date of the document in question </td>
	</tr>
	<tr>
			<td > <b> documentNumber </td>
			<td > String </td>
			<td > <b> true </td>
			<td > 0123456789 </td>
			<td> Number of document in question </td>
	</tr>
	<tr>
			<td > <b> entityType </td>
			<td > <b>ENUM</b></br> [INDIVIDUAL, </br> ORGANIZATION] </td>
			<td ><b> true </td>
			<td > INDIVIDUAL </td>
			<td> Entity type describes client status </td>
	</tr>
	<tr>
			<td > <b> identityDocumentType </td>
			<td > <b>ENUM</b></br>[PASSPORT, </br> IDENTITYCARD,</br> RESIDENCEPERMIT,</br> DRIVINGLICENSE,</br> REGISTRATIONCERTIFICATE,</br> OTHER] </td>
			<td ><b> true </td>
			<td > PASSPORT </td>
			<td> Identification document </td>
	</tr>
	</tbody>

</table>


## CountryOfTaxPaymentApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td> <b> country </td>
			<td > String </td>
			<td > <b>true </td>
			<td > LT </td>
			<td> Country of tax payment </td>
	</tr>
	<tr>
			<td > <b> taxpayerNumber </td>
			<td > String </td>
			<td > false </td>
			<td > 5541245574 </td>
			<td> The number of tax payer </td>
	</tr>
	</tbody>
</table>

## DeclaredTurnoverApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> from </td>
			<td > BigInteger </td>
			<td > true/false </td>
			<td> 1000 </td>
			<td> Amount range from.
At least one value (<From> or <To>)  must be specified </td>
	</tr>
	<tr>
			<td > <b> to </td>
			<td > String </td>
			<td > true/false </td>
			<td > 5000 </td>
			<td> Amount to.
At least one value (<From> or <To>)  must be specified </td>
	</tr>
	<tr>
			<td > <b> turnoverRange </td>
			<td ><b> ENUM </b></br> [SINGLE,</br> DAILY, </br> MONTHLY,</br> ANNUAL]  </td>
			<td ><b> true </td>
			<td > MONTHLY </td>
			<td> Range of declared turnover </td>
	</tr>
	<tr>
			<td > <b> turnoverType </td>
			<td > String </td>
			<td ><b>true </td>
			<td > TURNOVER_PER_MONTH </td>
			<td> Type of declared turnover. Classifier turnoverType </td>
	</tr>
	</tbody>
</table>

## IncomeSourceApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> from </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 100 </td>
			<td> Amount from </td>
	</tr>
	<tr>
			<td > <b> incomePercentage </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 5 </td>
			<td> Percentage of income from the source </td>
	</tr>
	<tr>
			<td > <b> incomeSourceType </td>
			<td > String </td>
			<td > <b> true </td>
			<td > SALARY </td>
			<td> Type of income source. Classifier incomeSourceType </td>
	</tr>
	<tr>
			<td > <b> to </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 1000 </td>
			<td> Amount to </td>
	</tr>
	</tbody>
</table>


## PaymentPurposeApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> paymentPurposeType </td>
			<td > String </td>
			<td > <b> true </td>
			<td > TAXES </td>
			<td> Type of income source, code of paymentPurposeType classifier </td>
	</tr>
	<tr>
			<td > <b> turnoverDirection </td>
			<td > <b> ENUM </b> </br> [INCOMING,</br>OUTGOING] </td>
			<td > <b> true </td>
			<td > OUT </td>
			<td> The turnover direction of payment </td>
	</tr>
	</tbody>
</table>

## SourceOfWealthApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> amount </td>
			<td > BigDecimal </td>
			<td > false </td>
			<td > 100000 </td>
			<td> Collected monetary amount </td>
	</tr>
	<tr>
			<td > <b> code </td>
			<td > String </td>
			<td > true </td>
			<td > INHERITANCE </td>
			<td> source of wealth type classifier </td>
	</tr>
	<tr>
			<td > <b> comment </td>
			<td > String </td>
			<td > false </td>
			<td >  </td>
			<td> Additional details about the source of wealth </td>
	</tr>
	</tbody>
</table>                 

## RelatedEntityApi

<table>
	<thead>
		<tr>
			<td > <b> field </td>
			<td > <b> type </td>
			<td > <b> mandatory </td>
			<td > <b> example </td>
			<td > <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td > <b> relationType </td>
			<td > String </td>
			<td > <b> true </td>
			<td > OWNER </td>
			<td> Type of relationship between entities. RelationType classifier </td>
	</tr>
	<tr>
			<td > <b> share </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 75 </td>
			<td> Shares owned by shareholders in the organization of the business entity </td>
	</tr>
	<tr>
			<td > <b> votePercentage </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 99 </td>
			<td> Vote percentage of shareholders in the organization of business entity </td>
	</tr>
	<tr>
			<td > <b> activityDescription  </td>
			<td > String </td>
			<td > false </td>
			<td > financial activity  </td>
			<td> Activity description of the related entity </td>
	</tr>
	<tr>
			<td > <b> birthCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> The birth country of the related entity </td>
	</tr>
	<tr>
			<td > <b> birthDate </td>
			<td > Date </td>
			<td > false </td>
			<td > 2000-05-28 </td>
			<td> Birth date of a related individual entity </td>
	</tr>
	<tr>
			<td > <b> country </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of the related entity </td>
	</tr>
	<tr>
			<td > <b> countryOfBusinessOperations </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of Business Operations of the related entity </td>
	</tr>
	<tr>
			<td > <b> entityType </td>
			<td >  <b>ENUM</b></br> [INDIVIDUAL, </br>ORGANIZATION] </td>
			<td > <b>true </td>
			<td > INDIVIDUAL </td>
			<td> Entity type describes client status </td>
	</tr>
	<tr>
			<td > <b> establishmentDate </td>
			<td > Date </td>
			<td > false </td>
			<td > 2020-05-30 </td>
			<td> Establishment date of related organization entity </td>
	</tr>
	<tr>
			<td > <b> extId </td>
			<td > String </td>
			<td > false </td>
			<td > 12345678912345 </td>
			<td> Used for screening callbacks to identify entity  </td>
	</tr>
	<tr>
			<td > <b> firstName </td>
			<td > String </td>
			<td > true/false </td>
			<td > John </td>
			<td> First name of related entity br><b>Mandatory</b> when entityType = INDIVIDUAL </br><b>Not Used</b>  when entityType = ORGANIZATION </td>
	</tr>
	<tr>
			<td > <b> isInAdverseMedia </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> An indication of the existence of information for an adverse media entity </td>
	</tr>
	<tr>
			<td > <b> isPEP </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> An indicator for a related individual entity is a politically exposed person </td>
	</tr>
	<tr>
			<td > <b> isSanctioned </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> Indicator for sanctions applied to the entity </td>
	</tr>
	<tr>
			<td > <b> lastName </td>
			<td > String </td>
			<td > true/false </td>
			<td > Rodriguez </td>
			<td> Last name of related entity </br><b>Mandatory</b> when entityType = INDIVIDUAL </br><b>Not Used</b>  when entityType = ORGANIZATION </td>
	</tr>
	<tr>
			<td > <b> legalForm </td>
			<td > String </td>
			<td > false </td>
			<td > COOPERATIVE </td>
			<td> Legal form of organization </td>
	</tr>
	<tr>
			<td > <b> nationalCode </td>
			<td > String </td>
			<td > false </td>
			<td > 123456789 </td>
			<td> National code or national identification number of individual. If a country does not issue national code, any other unique identifier can be used </td>
	</tr>
	<tr>
			<td > <b> regionOfActivityDescription </td>
			<td > String </td>
			<td > false </td>
			<td > EU </td>
			<td> Description of activity region of related entity </td>
	</tr>
	<tr>
			<td > <b> registrationCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of registration of related entity </td>
	</tr>
	<tr>
			<td > <b> relationDescription </td>
			<td > String </td>
			<td > false </td>
			<td > founder </td>
			<td> Description of the relationship between entities </td>
	</tr>
	<tr>
			<td > <b> title </td>
			<td > String </td>
			<td > true/ false </td>
			<td > Beko </td>
			<td> </br><b>Mandatory</b> when entityType = ORGANIZATION </br><b>Not Used</b>  when entityType = INDIVIDUAL </td>
	</tr>
	<tr>
			<td > <b> listActivity </td>
			<td > [ActivityApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activities of related entity </td>
	</tr>
	<tr>
			<td > <b> listAdditionalValues </td>
			<td > [AdditionalValueApi] </td>
			<td > false </td>
			<td > - </td>
			<td> Additional information about businessEntity </td>
	</tr>
	<tr>
			<td > <b> listAddress </td>
			<td > [AddressApi]  </td>
			<td > false </td>
			<td > - </td>
			<td> List of addresses </td>
	</tr>
	<tr>
			<td > <b> listBusinessEntityDocument </td>
			<td > [BusinessEntityDocumentApi] </td>
			<td > false </td>
			<td> - </td>
			<td> List of related entity document </td>
	</tr>
	<tr>
			<td > <b> listContact </td>
			<td > [ContactApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of contacts of related entity </td>
	</tr>
	<tr>
			<td > <b> listCountryOfActivity </td>
			<td > [countryOfActivity] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activity countries of related entity </td>
	</tr>
	<tr>
			<td > <b> listIncomeSource </td>
			<td > [IncomeSourceApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of income sources </td>
	</tr>
	<tr>
			<td > <b> listRegionOfActivity </td>
			<td > [regionOfActivity] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activity regions of related entity </td>
	</tr>
	</tbody>
</table>
		
