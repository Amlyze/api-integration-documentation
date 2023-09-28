# ORGANIZATION Fields 


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
			<td><b> CommunicationNumber </td>
			<td> String </td>
			<td><b> true </td>
			<td> ComNr_000321 </td>
			<td> Unique number of communication. used for risk assessment callback </td>
		</tr>
		<tr>
			<td><b> Requester  </td>
			<td> String </td>
			<td><b> true </td>
			<td>ComNr_000321 </td>
			<td> Name of the system requesting web service </td>
		</tr>
		<tr>
			<td><b> Action </td>
			<td> <b>ENUM</b> <br/>[CREATE (<i>default</i>), <br/> UPDATE] </td>
			<td> false </td>
			<td> UPDATE </td>
			<td> Element is used to change the data of an existing Customer. </br>❗ NOTE: all data will be replaced with newly received ones </td>
		</tr>
		<tr>
			<td><b> RiskManagementCategory </td>
			<td> String <br>(classifier) </td>
			<td><b> true </td>
			<td>IND_PK</td>
			<td>Code of risk management category for evaluation of the object.<br>💡 Possible values here are given just as an example, in the configuration period these could be updated</td>
		</tr>
		<tr>
			<td><b> SourceOfRiskLevel </td>
			<td> <b>ENUM</b><br>[IMPORT,EVALUATE] </td>
			<td><b> true </td>
			<td>IMPORT </td>
			<td>Source of risk level<br> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed. </br> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment</td>
		</tr>
		<tr>
			<td><b> RiskLevel </td>
			<td> <b>ENUM</b></br>[NONE,</br> LOW,</br> MEDIUM,</br> HIGH,</br> EXTREME]  </td>
			<td> true/false </b> </td>
			<td> HIGH </td>
			<td>The Risk Level of the customer during IMPORT</br><b>Mandatory</b> when sourceOfRiskLevel = IMPORT</br>
<b>Not Mandatory</b>  when sourceOfRiskLevel = EVALUATE</td>
		</tr>
		<tr>
			<td><b> InitializeScreeningProcesses </td>
			<td> String </td>
			<td> false </td>
			<td> SANCTIONS,<br>
PEP,</br> ADVERSE_MEDIA </td>
			<td>Defines which screening processes to initiate</td>
		</tr>
		<tr>
			<td><b> CustomerStatus</td>
			<td> <b>ENUM</b></br>[PENDING,</br>ACTIVE,</br> REJECTED,</br> SUSPENDED,</br>CLOSED] </td>
			<td><b> true </td>
			<td> ACTIVE</td>
			<td> Customer status represents the current standing or state of a customer's relationship with a business or organization </br> <i> PENDING - Customer application is received.</br> ACTIVE - Customer is onboarded ( account is provided or customer assessment case is resolved)</br> REJECTED - the customer for some reasons was rejected before opening an account for him. </br>SUSPENDED - Customer's activities for some reasons are restricted </br> CLOSED - Customer's profile is changed to being disabled </td>
		</tr>
		<tr>
			<td><b> CustomerExtId </td>
			<td> String </td>
			<td><b> true </td>
			<td> cust_1232</td>
			<td>Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution </td>
		</tr>
		<tr>
			<td><b> EntityType </td>
			<td> <b>ENUM</b></br>[ORGANIZATION] </td>
			<td><b> true </td>
			<td> ORGANIZATION </td>
			<td> Type bussines  entity </td>
		</tr>
		<tr>
			<td><b> NationalCode </td>
			<td> String </td>
			<td> false </td>
			<td> REG74121101 </td>
			<td>National code or national identification number of organization. If a country does not issue national code, any other unique identifier can be used:</br> <i>* Passport number;</br>* Social security number of person; </br> * A number of taxpayer or registration certificate of the company, etc </br> * A number of taxpayer or registration certificate of the company</td>
		</tr>
		<tr>
			<td><b> ApplicationDate </td>
			<td> Date </td>
			<td><b> true </td>
			<td> 2000-01-03 </td>
			<td>Date when customer first applied</td>
		</tr>
		<tr>
			<td><b> ActivityDescription </td>
			<td> String </td>
			<td>false </td>
			<td> financial activity </td>
			<td>Description of entity activity</td>
		</tr>
		<tr>
			<td><b> ActivityInRestrictedRegionDescription</td>
			<td> String </td>
			<td> false  </td>
			<td> logistics </td>
			<td> Description of business entities' activities in a restricted region </td>
		</tr>
        <tr>
			<td><b> ApprovalDate </td>
			<td> Date  </td>
			<td>false  </td>
			<td> 2000-01-03  </td>
			<td> Date of application approval </td>
		</tr>
        <tr>
			<td><b> ClosingDate  </td>
			<td>Date  </td>
			<td> true/false  </td>
			<td> 1995-05-24  </td>
			<td> Date of closure of all accounts </br><b>Mandatory</b> when customerStatus = CLOSED</br><b>Not Mandatory</b>  when customerStatus = PENDING, ACTIVE, REJECTED, SUSPENDED </td>
		</tr>
		<tr>
			<td><b> CompanyAssetValue  </td>
			<td> BigInteger  </td>
			<td> false  </td>
			<td> 100000   </td>
			<td> value of companies assets </td>
		</tr>
		<tr>
			<td><b> DoesCashDominate </td>
			<td> Boolean  </td>
			<td> false  </td>
			<td> true   </td>
			<td> Indicator for cash being the main income source </td>
		</tr>
		<tr>
			<td><b> EstablishmentDate  </td>
			<td> Date  </td>
			<td> false </td>
			<td> 2001-02-23  </td>
			<td> Establishment date for organization type entities </td>
		</tr>
        <tr>
			<td><b> GIIN  </td>
			<td> String </td>
			<td> false </td>
			<td> GIN548745122   </td>
			<td> Global intermediary identification number. </td>
		</tr>
		<tr>
			<td><b> HasMultiLayerStructure  </td>
			<td> Boolean  </td>
			<td> false  </td>
			<td> false   </td>
			<td> Check for multi-layer organizational structure </td>
		</tr>
        <tr>
			<td><b> IncomeSourceDescription </td>
			<td> String </td>
			<td>false </td>
			<td> work </td>
			<td> Description of income source of the entity </td>
		</tr>
		<tr>
			<td><b> InitialDepositAccount </td>
			<td> String </td>
			<td> false </td>
			<td> LT0000000000000000 </td>
			<td> Account of initial deposit </td>
		</tr>
		<tr>
			<td><b> InitialDepositAmount  </td>
			<td> Double  </td>
			<td> false </td>
			<td> 10000 </td>
			<td> Amount of initial deposit </td>
		</tr>
		<tr>
			<td><b> InitialDepositBank  </td>
			<td> String </td>
			<td> false </td>
			<td> BankBank  </td>
			<td> Bank of the initial deposit </td>
		</tr>
		<tr>
			<td><b> InitialDepositCurrency  </td>
			<td> String </td>
			<td> false </td>
			<td> EUR  </td>
			<td> Currency field notifies about the currency used in a certain operation. </td>
		</tr>
		<tr>
			<td ><b> InitialDepositSource  </td>
			<td> String </td>
			<td> false </td>
			<td> Dividend  </td>
			<td> Source of initial deposit </td>
		</tr>
        <tr>
			<td><b> IsActualAddressDeclared </td>
			<td> Boolean  </td>
			<td> false </td>
			<td> false  </td>
			<td> Whether customer declared ActualAddress  </td>
		</tr>
		<tr>
			<td><b> IsAudited  </td>
			<td> Boolean  </td>
			<td> false </td>
			<td> false  </td>
			<td> Indicator for the business entity being audited </td>
		</tr>
		<tr>
			<td><b> IsCorrespondenceAddressDeclared  </td>
			<td> Boolean  </td>
			<td> false </td>
			<td> true  </td>
			<td> Indicator for correspondence address declaration. </td>
		</tr>
		<tr>
			<td><b> IsDirectlyManaged </td>
			<td> Boolean  </td>
			<td> false </td>
			<td> false </td>
			<td> Check for direct management </td>
		</tr>
        <tr>
			<td><b> IsFinancialInstitution  </td>
			<td> Boolean  </td>
			<td> false </td>
			<td > false </td>
			<td> Whether entity is financial institution </td>
		</tr>
		<tr>
			<td><b> IsFined  </td>
			<td> Boolean </td>
			<td> false </td>
			<td> false </td>
			<td> Whether entity has fines </td>
		</tr>
		<tr>
			<td><b> IsInAdverseMedia  </td>
			<td> Boolean </td>
			<td> false </td>
			<td> true </td>
			<td> An indication of the existence of information for an adverse media entity </td>
		</tr>
        <tr>
			<td><b> IsLicenseRequired  </td>
			<td> Boolean  </td>
			<td> false </td>
			<td> true  </td>
			<td> Whether entity activity requires license </td>
		</tr>
		<tr>
			<td ><b> IsListed  </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> Indicator for the business entity is listed in stock exchange companies </td>
		</tr>
        <tr>
			<td ><b> IsRegulated  </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Indicator for the business entity being regulated by third-party authorities </td>
		</tr>
		<tr>
			<td ><b> IsSanctioned  </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Whether entity is sanctioned  </td>
		</tr>
        <tr>
			<td ><b> LegalForm  </td>
			<td > String  </td>
			<td > <b> true </td>
			<td > LTD </td>
			<td> Legal form of organization </td>
		</tr>
		<tr>
			<td ><b> LEI  </td>
			<td > String </td>
			<td > false </td>
			<td > LEI54511548  </td>
			<td>  LEI stands for Legal Entity Identifier, which is a unique code used to identify legal entities that participate in financial transactions </td>
		</tr>
		<tr>
			<td ><b> LicenseDescription  </td>
			<td > String </td>
			<td > false </td>
			<td > Licence No.4012 </td>
			<td> Business entities license description </td>
		</tr>
		<tr>
			<td ><b>  NoMajorShareHolders </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Check for no major shareholders involved </td>
		</tr>
		<tr>
			<td ><b> NumberOfAudits </td>
			<td > Integer </td>
			<td > false </td>
			<td > 6 </td>
			<td> The number of times a business entity has been audited </td>
		</tr>
		<tr>
			<td ><b> NumberOfEmployees </td>
			<td > Integer </td>
			<td > false </td>
			<td > 25 </td>
			<td> The number of employees in the company </td>
		</tr>
		<tr>
			<td ><b> OrganizationalStructureDescription </td>
			<td > String </td>
			<td > false </td>
			<td > Hierarchical </td>
			<td> Description of organization structure </td>
		</tr>
		<tr>
			<td ><b> PeriodsOfAuditsInYears </td>
			<td > integer </td>
			<td > false </td>
			<td > 3 </td>
			<td> The number of years that are in question for being audited </td>
		</tr>
		<tr>
			<td ><b> PeriodsOfFiningInYears </td>
			<td > integer </td>
			<td > false </td>
			<td > 3 </td>
			<td> The number of years that are in question for being fined </td>
		</tr>
        <tr>
			<td ><b> RegionOfActivityDescription </td>
			<td > String </td>
			<td > false </td>
			<td s> Customer service </td>
			<td> Description of the region for activities </td>
		</tr>
		<tr>
			<td ><b> RegistrationCountry </td>
			<td > String </td>
			<td ><b> true </td>
			<td > LT </td>
			<td> Country of registration of the organization </td>
		</tr>
        <tr>
			<td ><b> ThirdPartyServicesUsed </td>
			<td > String </td>
			<td > false </td>
			<td > true </td>
			<td> Whether client is using third party services </td>
		</tr>
		<tr>
			<td ><b> ThirdPartyServicesUsedDescription </td>
			<td > String </td>
			<td > false </td>
			<td > hosting </td>
			<td> Description of third party services </td>
		</tr>
		<tr>
			<td ><b> Title </td>
			<td > String </td>
			<td > <b>true</td>
			<td > Moller </td>
			<td> Title of organization entity</td>
		</tr>
        <tr>
			<td ><b> ListPurpose </td>
			<td > ENUM <br/><b>[BLACK,<br/> WHITE] </td>
			<td > false </td>
			<td > - </td>
			<td> Whether entity is black/white listed </td>
		</tr>
        <tr>
			<td ><b> ListActivity </td>
			<td > [ActivityApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activities </td>
		</tr>
		<tr>
			<td ><b> ListAdditionalValues </td>
			<td > [AdditionalValueApi] </td>
			<td > false </td>
			<td > - </td>
			<td> Additional information about businessEntity </td>
		</tr>
		<tr>
			<td ><b> ListAddress </td>
			<td > [AddressApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of addresses </td>
		</tr>
		<tr>
			<td ><b> ListAppealReason </td>
			<td > [AppealReasonType] </td>
			<td > false </td>
			<td > - </td>
			<td> List of reasons for the appeal </td>
		</tr>
		<tr>
			<td ><b> ListBusinessEntityDocument </td>
			<td > [BusinessEntityDocumentApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of related entity documents </td>
		</tr>
		<tr>
			<td ><b> ListContact </td>
			<td > [ContactApi] </td>
			<td > false </td>
			<td> - </td>
			<td> List of contacts of related entity </td>
		</tr>
		<tr>
			<td ><b> ListCountryOfActivity </td>
			<td > [countryOfActivity] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activity regions </td>
		</tr>
		<tr>
			<td ><b> ListCountryOfTaxPayment </td>
			<td > [CountryOfTaxPaymentApi] </td>
			<td> false </td>
			<td > - </td>
			<td> List of tax payment country </td>
		</tr>
		<tr>
			<td ><b> ListDeclaredTurnover </td>
			<td > [DeclaredTurnoverApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of declared turnover </td>
		</tr>
		<tr>
			<td ><b> ListIncomeSource </td>
			<td > [IncomeSourceApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of countries of payment </td>
		</tr>
		<tr>
			<td ><b> ListIntroductionSource </td>
			<td > [IntroductionSource] </td>
			<td > false </td>
			<td > - </td>
			<td> List of sources of introduction </td>
		</tr>
		<tr>
			<td ><b> ListOrderedService </td>
			<td > [serviceType] </td>
			<td > false </td>
			<td > - </td>
			<td> List of ordered services </td>
		</tr>
		<tr>
			<td ><b> ListPaymentCountry </td>
			<td > [country] </td>
			<td > false </td>
			<td > - </td>
			<td> List of payment country </td>
		</tr>
		<tr>
			<td ><b> ListPaymentPurpose </td>
			<td > [PaymentPurposeApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of payment purpose </td>
		</tr>
		<tr>
			<td ><b> ListRegionOfActivity </td>
			<td > [regionOfActivity] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activity countries of related entity </td>
		</tr>
		<tr>
			<td ><b> ListSourceOfWealth </td>
			<td > [SourceOfWealthApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of wealth sources </td>
		</tr>
		<tr>
			<td ><b> ListRelatedEntity </td>
			<td > [RelatedEntityApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List for related business entities </td>
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
			<td > <b> ActivityType </td>
			<td > String </td>
			<td > <b> true </td>
			<td > ACTIVITY_OTHER </td>
			<td> Type of business activity. Code from activity classifier </td>
	</tr>
	<tr>
			<td > <b> IncomePercentage </td>
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
			<td > <b> Code </td>
			<td > String </td>
			<td ><b> true </td>
			<td > related_to_usa </td>
			<td> Identifier for additional field</td>
	</tr>
	<tr>
			<td > <b> Datatype </td>
			<td > <b>ENUM </b></br>[STRING,</br> INTEGER,</br> DECIMAL,</br> DATE,</br> TIMESTAMP,</br> BOOLEAN\] </td>
			<td > <b>true </td>
			<td > STRING </td>
			<td> Type of provided value </td>
	</tr>
	</tbody>
	<tr>
			<td > <b> Description </td>
			<td > String </td>
			<td > <b>true </td>
			<td > entity has relation to USA </td>
			<td> human readable description of field </td>
	</tr>
	<tr>
			<td > <b> Value </td>
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
			<td > <b> AddressDetails </td>
			<td > String </td>
			<td > <b>true </td>
			<td > Verkiu 1, Vilnius </td>
			<td> Full address description </td>
	</tr>
	<tr>
			<td > <b> AddressType </td>
			<td > String </td>
			<td > false </td>
			<td > RESIDENCE </td>
			<td> Type of entity address. Classifier AddressType </td>
	</tr>
	<tr>
			<td > <b> City </td>
			<td > String </td>
			<td > false </td>
			<td > Vilnius </td>
			<td> City of given address </td>
	</tr>
	<tr>
			<td > <b> Country </td>
			<td > String </td>
			<td > <b>true </td>
			<td > LT </td>
			<td> Country of given addres. Classifier Country</td>
	</tr>
	<tr>
			<td > <b> Region </td>
			<td > String </td>
			<td > false </td>
			<td > EU </td>
			<td> Region of given address </td>
	</tr>
	<tr>
			<td > <b> StreetAddress </td>
			<td > String </td>
			<td > false </td>
			<td > Verkiu 1 </td>
			<td> Street, house and flat of given address </td>
	</tr>
	<tr>
			<td > <b> UseForCorrespondence </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Check for using the address in correspondence </td>
	</tr>
	<tr>
			<td > <b> ZipCode </td>
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
			<td > <b> Description </td>
			<td > String </td>
			<td > false </td>
			<td > passport </td>
			<td> Document description </td>
	</tr>
	<tr>
			<td > <b> DocumentExpiryDate </td>
			<td > Date </td>
			<td > false </td>
			<td > 2032-01-15  </td>
			<td> The expiry date of the document in question </td>
	</tr>
	<tr>
			<td > <b> DocumentIssueAuthority </td>
			<td > String </td>
			<td > <b>true </td>
			<td >migration office  </td>
			<td> An authority that issued the document. </td>
	</tr>
	<tr>
			<td > <b> DocumentIssueCountry </td>
			<td > String </td>
			<td ><b> true </td>
			<td > LT </td>
			<td> A country that issued the document </td>
	</tr>
	<tr>
			<td > <b> DocumentIssueDate </td>
			<td > Date </td>
			<td ><b> true </td>
			<td > 2022-01-15  </td>
			<td>Issue date of the document in question </td>
	</tr>
	<tr>
			<td > <b> DocumentNumber </td>
			<td > String </td>
			<td > <b> true </td>
			<td > 0123456789 </td>
			<td> Number of document in question </td>
	</tr>
	<tr>
			<td > <b> EntityType </td>
			<td > <b>ENUM</b></br> [INDIVIDUAL, </br> ORGANIZATION] </td>
			<td ><b> true </td>
			<td > ORGANIZATION </td>
			<td> Entity type describes client status </td>
	</tr>
	<tr>
			<td > <b> IdentityDocumentType </td>
			<td > <b>ENUM</b></br>[PASSPORT, </br> IDENTITYCARD,</br> RESIDENCEPERMIT,</br> DRIVINGLICENSE,</br> REGISTRATIONCERTIFICATE,</br> OTHER] </td>
			<td ><b> true </td>
			<td > REGISTRATIONCERTIFICATE </td>
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
			<td> <b> Country </td>
			<td > String </td>
			<td > <b>true </td>
			<td > LT </td>
			<td> Country of tax payment </td>
	</tr>
	<tr>
			<td > <b> TaxpayerNumber </td>
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
			<td > <b> From </td>
			<td > BigInteger </td>
			<td > true/false </td>
			<td> 1000 </td>
			<td> Amount range from.
At least one value (<From> or <To>)  must be specified </td>
	</tr>
	<tr>
			<td > <b> To </td>
			<td > String </td>
			<td > true/false </td>
			<td > 5000 </td>
			<td> Amount to.
At least one value (<From> or <To>)  must be specified </td>
	</tr>
	<tr>
			<td > <b> TurnoverRange </td>
			<td ><b> ENUM </b></br> [SINGLE,</br> DAILY, </br> MONTHLY,</br> ANNUAL]  </td>
			<td ><b> true </td>
			<td > MONTHLY </td>
			<td> Range of declared turnover </td>
	</tr>
	<tr>
			<td > <b> TurnoverType </td>
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
			<td > <b> From </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 100 </td>
			<td> Amount from </td>
	</tr>
	<tr>
			<td > <b> IncomePercentage </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 5 </td>
			<td> Percentage of income from the source </td>
	</tr>
	<tr>
			<td > <b> IncomeSourceType </td>
			<td > String </td>
			<td > <b> true </td>
			<td > SALARY </td>
			<td> Type of income source. Classifier incomeSourceType </td>
	</tr>
	<tr>
			<td > <b> To </td>
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
			<td > <b> PaymentPurposeType </td>
			<td > String </td>
			<td > <b> true </td>
			<td > TAXES </td>
			<td> Type of income source, code of paymentPurposeType classifier </td>
	</tr>
	<tr>
			<td > <b> TurnoverDirection </td>
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
			<td > <b> Amount </td>
			<td > BigDecimal </td>
			<td > false </td>
			<td > 100000 </td>
			<td> Collected monetary amount </td>
	</tr>
	<tr>
			<td > <b> Code </td>
			<td > String </td>
			<td > true </td>
			<td > INHERITANCE </td>
			<td> source of wealth type classifier </td>
	</tr>
	<tr>
			<td > <b> Comment </td>
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
			<td > <b> RelationType </td>
			<td > String </td>
			<td > <b> true </td>
			<td > OWNER </td>
			<td> Type of relationship between entities. RelationType classifier </td>
	</tr>
	<tr>
			<td > <b> Share </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 75 </td>
			<td> Shares owned by shareholders in the organization of the business entity </td>
	</tr>
	<tr>
			<td > <b> VotePercentage </td>
			<td > BigInteger </td>
			<td > false </td>
			<td > 99 </td>
			<td> Vote percentage of shareholders in the organization of business entity </td>
	</tr>
	<tr>
			<td > <b> ActivityDescription  </td>
			<td > String </td>
			<td > false </td>
			<td > financial activity  </td>
			<td> Activity description of the related entity </td>
	</tr>
	<tr>
			<td > <b> BirthCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> The birth country of the related entity </td>
	</tr>
	<tr>
			<td > <b> BirthDate </td>
			<td > Date </td>
			<td > false </td>
			<td > 2000-05-28 </td>
			<td> Birth date of a related individual entity </td>
	</tr>
	<tr>
			<td > <b> Country </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of the related entity </td>
	</tr>
	<tr>
			<td > <b> CountryOfBusinessOperations </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of Business Operations of the related entity </td>
	</tr>
	<tr>
			<td > <b> EntityType </td>
			<td >  <b>ENUM</b></br> [INDIVIDUAL, </br>ORGANIZATION] </td>
			<td > <b>true </td>
			<td > INDIVIDUAL </td>
			<td> Entity type describes client status </td>
	</tr>
	<tr>
			<td > <b> EstablishmentDate </td>
			<td > Date </td>
			<td > false </td>
			<td > 2020-05-30 </td>
			<td> Establishment date of related organization entity </td>
	</tr>
	<tr>
			<td > <b> ExtId </td>
			<td > String </td>
			<td > false </td>
			<td > 12345678912345 </td>
			<td> Used for screening callbacks to identify entity  </td>
	</tr>
	<tr>
			<td > <b> FirstName </td>
			<td > String </td>
			<td > true/false </td>
			<td > John </td>
			<td> First name of related entity br><b>Mandatory</b> when entityType = INDIVIDUAL </br><b>Not Used</b>  when entityType = ORGANIZATION </td>
	</tr>
	<tr>
			<td > <b> IsInAdverseMedia </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> An indication of the existence of information for an adverse media entity </td>
	</tr>
	<tr>
			<td > <b> IsPEP </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> An indicator for a related individual entity is a politically exposed person </td>
	</tr>
	<tr>
			<td > <b> IsSanctioned </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> Indicator for sanctions applied to the entity </td>
	</tr>
	<tr>
			<td > <b> LastName </td>
			<td > String </td>
			<td > true/false </td>
			<td > Rodriguez </td>
			<td> Last name of related entity </br><b>Mandatory</b> when entityType = INDIVIDUAL </br><b>Not Used</b>  when entityType = ORGANIZATION </td>
	</tr>
	<tr>
			<td > <b> LegalForm </td>
			<td > String </td>
			<td > false </td>
			<td > COOPERATIVE </td>
			<td> Legal form of organization </td>
	</tr>
	<tr>
			<td > <b> NationalCode </td>
			<td > String </td>
			<td > false </td>
			<td > 123456789 </td>
			<td> National code or national identification number of individual or organization. If a country does not issue national code, any other unique identifier can be used </td>
	</tr>
	<tr>
			<td > <b> RegionOfActivityDescription </td>
			<td > String </td>
			<td > false </td>
			<td > EU </td>
			<td> Description of activity region of related entity </td>
	</tr>
	<tr>
			<td > <b> RegistrationCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of registration of related entity </td>
	</tr>
	<tr>
			<td > <b> RelationDescription </td>
			<td > String </td>
			<td > false </td>
			<td > founder </td>
			<td> Description of the relationship between entities </td>
	</tr>
	<tr>
			<td > <b> Title </td>
			<td > String </td>
			<td > true/ false </td>
			<td > Beko </td>
			<td> </br><b>Mandatory</b> when entityType = INDIVIDUAL </br><b>Not Used</b>  when entityType = ORGANIZATION </td>
	</tr>
	<tr>
			<td > <b> ListActivity </td>
			<td > [ActivityApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activities of related entity </td>
	</tr>
	<tr>
			<td > <b> ListAdditionalValues </td>
			<td > [AdditionalValueApi] </td>
			<td > false </td>
			<td > - </td>
			<td> Additional information about businessEntity </td>
	</tr>
	<tr>
			<td > <b> ListAddress </td>
			<td > [AddressApi]  </td>
			<td > false </td>
			<td > - </td>
			<td> List of addresses </td>
	</tr>
	<tr>
			<td > <b> ListBusinessEntityDocument </td>
			<td > [BusinessEntityDocumentApi] </td>
			<td > false </td>
			<td> - </td>
			<td> List of related entity document </td>
	</tr>
	<tr>
			<td > <b> ListContact </td>
			<td > [ContactApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of contacts of related entity </td>
	</tr>
	<tr>
			<td > <b> ListCountryOfActivity </td>
			<td > [countryOfActivity] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activity countries of related entity </td>
	</tr>
	<tr>
			<td > <b> ListIncomeSource </td>
			<td > [IncomeSourceApi] </td>
			<td > false </td>
			<td > - </td>
			<td> List of income sources </td>
	</tr>
	<tr>
			<td > <b> ListRegionOfActivity </td>
			<td > [regionOfActivity] </td>
			<td > false </td>
			<td > - </td>
			<td> List of activity regions of related entity </td>
	</tr>
	</tbody>
</table>