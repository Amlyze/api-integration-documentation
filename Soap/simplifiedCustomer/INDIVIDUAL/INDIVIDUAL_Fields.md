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
			<td> <b>ENUM</b></br>[INDIVIDUAL] </td>
			<td><b> true </td>
			<td> INDIVIDUAL </td>
			<td> Whether bussines or individual entity </td>
		</tr>
		<tr>
			<td><b> CustomerExtId </td>
			<td> String </td>
			<td><b> true </td>
			<td> cust_1232</td>
			<td>Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution </td>
		</tr>
        <tr>
			<td><b> FirstName </td>
			<td> String </td>
			<td> <b>true </td>
			<td> Jose  </td>
			<td> First name of individual entity </td>
		</tr>
        <tr>
			<td ><b> LastName  </td>
			<td > String </td>
			<td > <b>true </td>
			<td > Rodriguez </td>
			<td> Last name of individual entity  </td>
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
			<td>National code or national identification number of individual. If a country does not issue national code, any other unique identifier can be used:</br> <i>* Passport number;</br>* Social security number of person; </br> * A number of taxpayer or registration certificate of the company, etc </br> * A number of taxpayer or registration certificate of the company</td>
		</tr>
		<tr>
			<td><b> ApplicationDate </td>
			<td> Date </td>
			<td><b> false </td>
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
			<td><b> AmlOfficer</td>
			<td>Boolean </td>
			<td><b> false </td>
			<td> false </td>
			<td> Indicator for the person being AML officer </td>
		</tr>
		<tr>
			<td><b> ApprovalDate </td>
			<td> Date  </td>
			<td>false  </td>
			<td> 2000-01-03  </td>
			<td> Date of application approval </td>
		</tr>
		<tr>
			<td><b> BirthCountry  </td>
			<td>String </td>
			<td> <b>false  </td>
			<td> LT </td>
			<td> Country of birth of individual entity </td>
		</tr>
		<tr>
			<td><b> BirthDate </td>
			<td> Date  </td>
			<td> <b>false  </td>
			<td> 1995-05-24  </td>
			<td> Date of birth of individual entity</td>
		</tr>
		<tr>
			<td><b> CitizenshipCountry  </td>
			<td> String </td>
			<td><b> false </td>
			<td> LT  </td>
			<td> Country of citizenship of individual entity </td>
		</tr>
		<tr>
			<td><b> ClosingDate  </td>
			<td>Date  </td>
			<td> false  </td>
			<td> 1995-05-24  </td>
			<td> Date of closure of all accounts </td>
		</tr>
        <tr>
			<td><b> DoesCashDominate </td>
			<td> Boolean  </td>
			<td> false  </td>
			<td> true   </td>
			<td> Indicator for cash being the main income source </td>
		</tr>
        <tr>
			<td><b> IncomeSourceDescription </td>
			<td> String </td>
			<td>false </td>
			<td> work </td>
			<td> Description of income source of the entity </td>
		</tr>
		<tr>
			<td><b> IncomingPaymentDescription </td>
			<td> String </td>
			<td> false </td>
			<td> payment for work </td>
			<td> Description of incoming payment operation </td>
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
			<td><b> IsFamilyPEP  </td>
			<td> Boolean </td>
			<td> false </td>
			<td> false </td>
			<td> Identification of whether or not a family member of an Individual entity is politically exposed </td>
		</tr>
        <tr>
			<td><b> IsInAdverseMedia  </td>
			<td> Boolean </td>
			<td> false </td>
			<td> true </td>
			<td> An indication of the existence of information for an adverse media entity </td>
		</tr>
		<tr>
			<td><b> IsLegalResident  </td>
			<td> Boolean  </td>
			<td> false </td>
			<td > true </td>
			<td> Indicator for whether or not the individual entity is a legal resident </td>
		</tr>
        <tr>
			<td ><b> IsLitigated  </td>
			<td > Boolean </td>
			<td > false </td>
			<td > false </td>
			<td> Indicator for the person being litigated </td>
		</tr>
		<tr>
			<td ><b> IsPEP  </td>
			<td > Boolean  </td>
			<td > false </td>
			<td > false </td>
			<td> Identification for whether or not a person is politically exposed </td>
		</tr>
        <tr>
			<td ><b> IsSanctioned  </td>
			<td > Boolean </td>
			<td > false </td>
			<td > true </td>
			<td> Whether entity is sanctioned  </td>
		</tr>
        <tr>
			<td ><b> PermanentResidenceCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of permanent residency of an individual entity </td>
		</tr>
        <tr>
			<td ><b> SecondCitizenshipCountry </td>
			<td > String </td>
			<td > false </td>
			<td > LT </td>
			<td> Country of second citizenship of individual entity </td>
		</tr>
        <tr>
			<td ><b> ListPurpose </td>
			<td > ENUM <br/><b>[BLACK,<br/> WHITE] </td>
			<td > false </td>
			<td > - </td>
			<td> Whether entity is black/white listed </td>
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
                <td > <b> AddressType </td>
                <td > String </td>
                <td > false </td>
                <td > RESIDENCE </td>
                <td> Type of entity address. Classifier AddressType </td>
        </tr>
        <tr>
                <td > <b> AddressDetails </td>
                <td > String </td>
                <td > <b>true </td>
                <td > Verkiu 1, Vilnius </td>
                <td> Full address description </td>
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
                <td > <b> ZipCode </td>
                <td > String </td>
                <td > false </td>
                <td > 12345 </td>
                <td> Zip code of the address </td>
        </tr>
        <tr>
                <td > <b> UseForCorrespondence </td>
                <td > Boolean </td>
                <td > false </td>
                <td > true </td>
                <td> Check for using the address in correspondence </td>
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
            <td > <b> EntityType </td>
            <td > <b>ENUM</b></br> [INDIVIDUAL, </br> ORGANIZATION] </td>
            <td ><b> true </td>
            <td > INDIVIDUAL </td>
            <td> Entity type describes client status </td>
        </tr>
        <tr>
            <td > <b> IdentityDocumentType </td>
            <td > <b>ENUM</b></br>[PASSPORT, </br> IDENTITYCARD,</br> RESIDENCEPERMIT,</br> DRIVINGLICENSE,</br> REGISTRATIONCERTIFICATE,</br> OTHER] </td>
            <td ><b> true </td>
            <td > PASSPORT </td>
            <td> Identification document </td>
        </tr>
        <tr>
            <td > <b> DocumentNumber </td>
            <td > String </td>
            <td > <b> true </td>
            <td > 0123456789 </td>
            <td> Number of document in question </td>
        </tr>
        <tr>
            <td > <b> DocumentIssueDate </td>
            <td > Date </td>
            <td ><b> true </td>
            <td > 2022-01-15  </td>
            <td>Issue date of the document in question </td>
        </tr>
        <tr>
            <td > <b> DocumentExpiryDate </td>
            <td > Date </td>
            <td > false </td>
            <td > 2032-01-15  </td>
            <td> The expiry date of the document in question </td>
        </tr>
        <tr>
            <td > <b> DocumentIssueCountry </td>
            <td > String </td>
            <td ><b> true </td>
            <td > LT </td>
            <td> A country that issued the document </td>
        </tr>
        <tr>
            <td > <b> DocumentIssueAuthority </td>
            <td > String </td>
            <td > <b>true </td>
            <td > passport department </td>
            <td> An authority that issued the document. </td>
        </tr>
        <tr>
            <td > <b> Description </td>
            <td > String </td>
            <td > <b>false </td>
            <td > Main identification document </td>
            <td> Description. </td>
        </tr>
	</tbody>
</table>

## ContactApi

TODO 