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
			<td>Bank_system </td>
			<td> Name of the system requesting web service </td>
		</tr>
		<tr>
			<td><b> RiskManagementCategory </td>
			<td> String <br>(classifier) </td>
			<td><b> true </td>
			<td>FAST</td>
			<td>Code of risk management category for evaluation of the object.<br>💡 Possible values here are given just as an example, in the configuration period these could be updated</td>
		</tr>
		<tr>
			<td><b> EntityType </td>
			<td> <b>ENUM</b></br>[ORGANIZATION] </td>
			<td><b> true </td>
			<td> ORGANIZATION </td>
			<td> Type bussines  entity </td>
		</tr>
		<tr>
			<td><b> CustomerExtId </td>
			<td> String </td>
			<td><b> true </td>
			<td> cust_1232</td>
			<td>Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution </td>
		</tr>
		<tr>
			<td ><b> Title </td>
			<td > String </td>
			<td > <b>true</td>
			<td > UAB "Dockers" </td>
			<td> Title of organization entity</td>
		</tr>
		<tr>
			<td><b> CustomerStatus</td>
			<td> <b>ENUM</b></br>[PENDING,</br>ACTIVE,</br> REJECTED,</br> SUSPENDED,</br>CLOSED] </td>
			<td><b> true </td>
			<td> ACTIVE</td>
			<td> Customer status represents the current standing or state of a customer's relationship with a business or organization </br> <i> PENDING - Customer application is received.</br> ACTIVE - Customer is onboarded ( account is provided or customer assessment case is resolved)</br> REJECTED - the customer for some reasons was rejected before opening an account for him. </br>SUSPENDED - Customer's activities for some reasons are restricted </br> CLOSED - Customer's profile is changed to being disabled </td>
		</tr>
		<tr>
			<td><b> RiskLevel </td>
			<td> <b>ENUM</b></br>[NONE,</br> LOW,</br> MEDIUM,</br> HIGH,</br> EXTREME]  </td>
			<td> false </b> </td>
			<td> HIGH </td>
			<td>The Risk Level of the customer. Default value is NONE.</td>
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
			<td><b> NationalCode </td>
			<td> String </td>
			<td> false </td>
			<td> REG74121101 </td>
			<td>National code or national identification number of organization. If a country does not issue national code, any other unique identifier can be used:</br> <i>* Passport number;</br>* Social security number of person; </br> * A number of taxpayer or registration certificate of the company, etc </br> * A number of taxpayer or registration certificate of the company</td>
		</tr>
		<tr>
			<td><b> ApplicationDate </td>
			<td> Date </td>
			<td> false </td>
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
			<td> false  </td>
			<td> 2005-05-24  </td>
			<td> Date of closure of all accounts </td>
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
			<td > false </td>
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
			<td > false </td>
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
	</tbody>
</table>
