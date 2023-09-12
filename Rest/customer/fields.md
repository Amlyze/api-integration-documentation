# Customers fields 
<table>
	<thead>
		<tr>
			<td style="text-align:center"><b> field </td>
			<td style="text-align:center"><b> type </td>
			<td style="text-align:center"><b> mandatory </td>
			<td style="text-align:center"><b> example </td>
			<td style="text-align:center"><b> description </td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align:center"><b> communicationNumber </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> ComNr_000321 </td>
			<td> Unique number of communication. used for risk assessment callback </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> requester  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> ComNr_000321 </td>
			<td> Name of the system requesting web service </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> action </td>
			<td style="text-align:center"> <b>ENUM</b> <br/>[CREATE (<i>default</i>), <br/> UPDATE] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> UPDATE </td>
			<td> Element is used to change the data of an existing Customer. </br>❗ NOTE: all data will be replaced with newly received ones </td>
		</tr>
		<tr>
			<td style="text-align:center"><b>riskManagementCategory </td>
			<td style="text-align:center"> String <br>(classifier) </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center">IND_PK</td>
			<td>Code of risk management category for evaluation of the object.<br>💡 Possible values here are given just as an example, in the configuration period these could be updated</td>
		</tr>
		<tr>
			<td style="text-align:center"><b>sourceOfRiskLevel </td>
			<td style="text-align:center"> <b>ENUM</b><br>
[IMPORT,
EVALUATE] </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center">IMPORT </td>
			<td>Source of risk level<br> The value <b>"EVALUATE"</b> should be used for normal business processes - risk assessment will be performed. </br> The value <b>"IMPORT"</b> should be used for migration purposes only – the customer and it's questionnaire will be imported without risk assessment</td>
		</tr>
		<tr>
			<td style="text-align:center"><b> riskLevel </td>
			<td style="text-align:center"> <b>ENUM</b></br>[NONE,</br> LOW,</br> MEDIUM,</br> HIGH,</br> EXTREME]  </td>
			<td style="text-align:center"> true/false </b> </td>
			<td style="text-align:center"> HIGH </td>
			<td>The Risk Level of the customer during IMPORT</br><b>Mandatory</b> when sourceOfRiskLevel = IMPORT</br>
<b>Not Mandatory</b>  when sourceOfRiskLevel = EVALUATE</td>
		</tr>
		<tr>
			<td style="text-align:center"><b> initializeScreeningProcesses </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> SANCTIONS,<br>
PEP,</br> ADVERSE_MEDIA </td>
			<td>Defines which screening processes to initiate</td>
		</tr>
		<tr>
			<td style="text-align:center"><b>customerStatus</td>
			<td style="text-align:center"> <b>ENUM</b></br>[PENDING,</br>ACTIVE,</br> REJECTED,</br> SUSPENDED,</br>CLOSED] </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center">ACTIVE</td>
			<td> Customer status represents the current standing or state of a customer's relationship with a business or organization </br> <i> PENDING - Customer application is received.</br> ACTIVE - Customer is onboarded ( account is provided or customer assessment case is resolved)</br> REJECTED - the customer for some reasons was rejected before opening an account for him. </br>SUSPENDED - Customer's activities for some reasons are restricted </br> CLOSED - Customer's profile is changed to being disabled </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> customerExtId </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> cust_1232</td>
			<td>Unique external customer identifier. The identifier corresponds to the client's identifier in the financial institution </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> entityType </td>
			<td style="text-align:center"> <b>ENUM</b></br>[INDIVIDUAL, </br>
ORGANIZATION] </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> INDIVIDUAL </td>
			<td> Whether bussines or individual entity </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> nationalCode </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> REG74121101 </td>
			<td>National code or national identification number of individual or organization. If a country does not issue national code, any other unique identifier can be used:</br> <i>* Passport number;</br>* Social security number of person; </br> * A number of taxpayer or registration certificate of the company, etc </br> * A number of taxpayer or registration certificate of the company</td>
		</tr>
		<tr>
			<td style="text-align:center"><b> applicationDate </td>
			<td style="text-align:center"> Date </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> 2000-01-03 </td>
			<td>Date when customer first applied</td>
		</tr>
		<tr>
			<td style="text-align:center"><b> activityDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> financial activity </td>
			<td>Description of entity activity</td>
		</tr>
		<tr>
			<td style="text-align:center"><b>activityInRestrictedRegionDescription</td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false  </td>
			<td style="text-align:center"> logistics </td>
			<td> Description of business entities' activities in a restricted region </td>
		</tr>
		<tr>
			<td style="text-align:center"><b>amlOfficer</td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"><b> false </td>
			<td style="text-align:center"> false </td>
			<td> Indicator for the person being AML officer </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> approvalDate </td>
			<td style="text-align:center"> Date  </td>
			<td style="text-align:center"> false  </td>
			<td style="text-align:center"> 2000-01-03  </td>
			<td> Date of application approval </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> birthCountry  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false  </td>
			<td style="text-align:center"> LT </td>
			<td> Country of birth of individual entity </br><b>Mandatory</b> when entityType = INDIVIDUAL</br>
<b>Not Used</b>  when entityType = ORGANIZATION</td>
		</tr>
		<tr>
			<td style="text-align:center"><b> birthDate   </td>
			<td style="text-align:center"> Date  </td>
			<td style="text-align:center"> true/false  </td>
			<td style="text-align:center"> 1995-05-24  </td>
			<td> Date of birth of individual entity </br><b>Mandatory</b> when entityType = INDIVIDUAL</br>
<b>Not Used</b>  when entityType = ORGANIZATION </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> citizenshipCountry  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> LT  </td>
			<td> Country of citizenship of individual entity </br><b>Mandatory</b> when entityType = INDIVIDUAL</br>
<b>Not Used</b>  when entityType = ORGANIZATION </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> closingDate  </td>
			<td style="text-align:center"> Date  </td>
			<td style="text-align:center"> true/false  </td>
			<td style="text-align:center"> 1995-05-24  </td>
			<td> Date of closure of all accounts </br><b>Mandatory</b> when customerStatus = CLOSED</br><b>Not Mandatory</b>  when customerStatus = PENDING, ACTIVE, REJECTED, SUSPENDED </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> companyAssetValue  </td>
			<td style="text-align:center"> BigInteger  </td>
			<td style="text-align:center"> false  </td>
			<td style="text-align:center"> 100000   </td>
			<td> value of companies assets </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> doesCashDominate </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false  </td>
			<td style="text-align:center"> true   </td>
			<td> Indicator for cash being the main income source </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> establishmentDate  </td>
			<td style="text-align:center"> Date  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 2001-02-23  </td>
			<td> Establishment date for organization type entities </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> firstName </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> Jose  </td>
			<td> First name of individual entity </br><b>Mandatory</b> when customerStatus = CLOSED</br><b>Not Mandatory</b>  when customerStatus = PENDING, ACTIVE, REJECTED, SUSPENDED </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> GIIN  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> GIN548745122   </td>
			<td> Global intermediary identification number. </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> hasMultiLayerStructure  </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false  </td>
			<td style="text-align:center"> false   </td>
			<td> Check for multi-layer organizational structure </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> incomeSourceDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> work </td>
			<td> Description of income source of the entity </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> incomingPaymentDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> payment for work </td>
			<td> Description of incoming payment operation </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> initialDepositAccount </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT0000000000000000 </td>
			<td> Account of initial deposit </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> initialDepositAmount  </td>
			<td style="text-align:center"> Double  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 10000 </td>
			<td> Amount of initial deposit </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> initialDepositBank  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> BankBank  </td>
			<td> Bank of the initial deposit </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> initialDepositCurrency  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> EUR  </td>
			<td> Currency field notifies about the currency used in a certain operation. </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> initialDepositSource  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Dividend  </td>
			<td> Source of initial deposit </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isActualAddressDeclared </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false  </td>
			<td> Whether customer declared ActualAddress  </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isAudited  </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false  </td>
			<td> Indicator for the business entity being audited </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isCorrespondenceAddressDeclared  </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true  </td>
			<td> Indicator for correspondence address declaration. </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isDirectlyManaged </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> Check for direct management </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isFamilyPEP  </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> Identification of whether or not a family member of an Individual entity is politically exposed </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isFinancialInstitution  </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> Whether entity is financial institution </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isFined  </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> Whether entity has fines </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isInAdverseMedia  </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> An indication of the existence of information for an adverse media entity </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isLegalResident  </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Indicator for whether or not the individual entity is a legal resident </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isLicenseRequired  </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true  </td>
			<td> Whether entity activity requires license </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isListed  </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> Indicator for the business entity is listed in stock exchange companies </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isLitigated  </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> Indicator for the person being litigated </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isPEP  </td>
			<td style="text-align:center"> Boolean  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> Identification for whether or not a person is politically exposed </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isRegulated  </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Indicator for the business entity being regulated by third-party authorities </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isSanctioned  </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Whether entity is sanctioned  </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> lastName  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> Rodriguez </td>
			<td> Last name of individual </br><b>Mandatory</b> when entityType = INDIVIDUAL</br><b>Not Used</b>  when entityType = ORGANIZATION </td> </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> legalForm  </td>
			<td style="text-align:center"> String  </td>
			<td style="text-align:center"> <b> true </td>
			<td style="text-align:center"> LTD </td>
			<td> Legal form of organization </br><b>Mandatory</b> when entityType = ORGANIZATION</br><b>Not Used</b>  when entityType = INDIVIDUAL  </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> LEI  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LEI54511548  </td>
			<td>  LEI stands for Legal Entity Identifier, which is a unique code used to identify legal entities that participate in financial transactions </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> licenseDescription  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Licence No.4012 </td>
			<td> Business entities license description </td>
		</tr>
		<tr>
			<td style="text-align:center"><b>  noMajorShareHolders </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Check for no major shareholders involved </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> numberOfAudits </td>
			<td style="text-align:center"> Integer </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 6 </td>
			<td> The number of times a business entity has been audited </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> numberOfEmployees </td>
			<td style="text-align:center"> Integer </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 25 </td>
			<td> The number of employees in the company </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> organizationalStructureDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Hierarchical </td>
			<td> Description of organization structure </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> outgoingPaymentDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Payment for the No.412 agreement </td>
			<td> Description of outgoing payment operation </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> periodsOfAuditsInYears </td>
			<td style="text-align:center"> integer </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 3 </td>
			<td> The number of years that are in question for being audited </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> periodsOfFiningInYears </td>
			<td style="text-align:center"> integer </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 3 </td>
			<td> The number of years that are in question for being fined </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> permanentResidenceCountry </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT </td>
			<td> Country of permanent residency of an individual entity </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> regionOfActivityDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Customer service </td>
			<td> Description of the region for activities </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> registrationCountry </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> LT </td>
			<td> Country of registration of the organization </br><b>Mandatory</b> when entityType = ORGANIZATION</br><b>Not Mandatory</b>  when entityType = INDIVIDUAL </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> secondCitizenshipCountry </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT </td>
			<td> Country of second citizenship of individual entity </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> thirdPartyServicesUsed </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Whether client is using third party services </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> thirdPartyServicesUsedDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> hosting </td>
			<td> Description of third party services </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> title </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> Moller </td>
			<td> title of organization entity</br> for individual generated (firstName + "  + lastName) </br><b>Mandatory</b> when entityType = ORGANIZATION</br><b>Not Used</b>  when entityType = INDIVIDUAL </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listPurpose </td>
			<td style="text-align:center"> ENUM <br/><b>[BLACK,<br/> WHITE] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> Whether entity is black/white listed </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> fieldOfActivity </td>
			<td style="text-align:center"> FieldOfActivityApi </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> Information about the activities </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listActivity </td>
			<td style="text-align:center"> [ActivityApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of activities </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listAdditionalValues </td>
			<td style="text-align:center"> [AdditionalValueApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> Additional information about businessEntity </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listAddress </td>
			<td style="text-align:center"> [AddressApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of addresses </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listAppealReason </td>
			<td style="text-align:center"> [AppealReasonType] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of reasons for the appeal </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listBusinessEntityDocument </td>
			<td style="text-align:center"> [BusinessEntityDocumentApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of related entity documents </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listContact </td>
			<td style="text-align:center"> [ContactApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of contacts of related entity </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listCountryOfActivity </td>
			<td style="text-align:center"> [countryOfActivity] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of activity regions </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listCountryOfTaxPayment </td>
			<td style="text-align:center"> [CountryOfTaxPaymentApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of tax payment country </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listDeclaredTurnover </td>
			<td style="text-align:center"> [DeclaredTurnoverApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of declared turnover </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listIncomeSource </td>
			<td style="text-align:center"> [IncomeSourceApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of countries of payment </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listIntroductionSource </td>
			<td style="text-align:center"> [IntroductionSource] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of sources of introduction </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listOrderedService </td>
			<td style="text-align:center"> [serviceType] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of ordered services </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listPaymentCountry </td>
			<td style="text-align:center"> [country] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of payment country </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listPaymentPurpose </td>
			<td style="text-align:center"> [PaymentPurposeApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of payment purpose </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listRegionOfActivity </td>
			<td style="text-align:center"> [regionOfActivity] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of activity countries of related entity </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listSourceOfWealth </td>
			<td style="text-align:center"> [SourceOfWealthApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of wealth sources </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> listRelatedEntity </td>
			<td style="text-align:center"> [RelatedEntityApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List for related business entities </td>
		</tr>
	</tbody>
</table>



# Customers fields
                                                           


## FieldOfActivityApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align:center"> <b> employment </td>
			<td style="text-align:center"> FieldEmploymentApi </td>
			<td style="text-align:center"> false </td>
		</tr>
		<tr>
			<td style="text-align:center"> <b> other </td>
			<td style="text-align:center"> FieldOtherApi </td>
			<td style="text-align:center"> false </td>
		</tr>
		<tr>
			<td style="text-align:center"> <b> pension </td>
			<td style="text-align:center"> FieldPensionApi </td>
			<td style="text-align:center"> false </td>
		</tr>
		<tr>
			<td style="text-align:center"> <b> student </td>
			<td style="text-align:center"> FieldStudentApi </td>
			<td style="text-align:center"> false </td>
		</tr>
	</tbody>
</table>

**FieldEmploymentApi**

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td style="text-align:center"><b> employerTitle </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> CompanyB  </td>
			<td> Title of the individual employer. </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> employmentPositionDescription </td>
			<<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Software Engineer  </td>
			<td> Description of the individual employment position.  </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isEmployee </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false  </td>
			<td> Indicator for the individual entity being an employee </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isSelfEmployed </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false  </td>
			<td> Indicator for the individual entity being self-employed </td>
		</tr>
		<tr>
			<td style="text-align:center"><b> isUnemployed </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false  </td>
			<td> Indicator for the individual entity being unemployed </td>
		</tr>
	</tbody>
</table>



**FieldOtherApi**

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> isOtherStatus </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Indicator for other status individual </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> otherStatusDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> consultation </td>
			<td> Description of other status </td>
	</tr>
	</tbody>
</table>


**FieldPensionApi**

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> isPensioner </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Indicator for the individual entity being a pensioner </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> pensionCountry </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT </td>
			<td> The country is responsible for paying an individual's pension </td>
	</tr>
	</tbody>
</table>


**FieldStudentApi**

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> higherSchoolCountry </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT </td>
			<td> Indicator for individual entity being a studen </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> higherSchoolTitle </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Vilniaus Universitetas MIF </td>
			<td> Title of higher school of the student </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> isStudent </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Country of higher school of the student </td>
	</tr>
	</tbody>
</table>

## ActivityApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> activityType </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b> true </td>
			<td style="text-align:center"> ACTIVITY_OTHER </td>
			<td> Type of business activity. Code from activity classifier </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> incomePercentage </td>
			<td style="text-align:center"> BigInteger </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center">15  </td>
			<td> Percentage of income from certain activity </td>
	</tr>
	</tbody>
</table>


## AdditionalValueApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> code </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> related_to_usa </td>
			<td> identifier for additional field</td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> datatype </td>
			<td style="text-align:center"> <b>ENUM </b></br>[STRING,</br> INTEGER,</br> DECIMAL,</br> DATE,</br> TIMESTAMP,</br> BOOLEAN\] </td>
			<td style="text-align:center"> <b>true </td>
			<td style="text-align:center"> STRING </td>
			<td> Type of provided value </td>
	</tr>
	</tbody>
	<tr>
			<td style="text-align:center"> <b> description </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b>true </td>
			<td style="text-align:center"> entity has relation to USA </td>
			<td> human readable description of field </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> value </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> true </td>
			<td> value of field </td>
	</tr>
	</tbody>
	
</table>


## AddressApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> addressDetails </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b>true </td>
			<td style="text-align:center"> Verkiu 1, Vilnius </td>
			<td> Full address description </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> addressType </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> RESIDENCE </td>
			<td> Type of entity address. Classifier AddressType </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> city </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Vilnius </td>
			<td> City of given address </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> country </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b>true </td>
			<td style="text-align:center"> LT </td>
			<td> Country of given addres. Classifier Country</td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> region </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> EU </td>
			<td> Region of given address </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> streetAddress </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> Verkiu 1 </td>
			<td> Street, house and flat of given address </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> useForCorrespondence </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> true </td>
			<td> Check for using the address in correspondence </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> zipCode </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 12345 </td>
			<td> Zip code of the address </td>
	</tr>
	</tbody>
</table>


## BusinessEntityDocumentApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> description </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> passport </td>
			<td> Document description </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> documentExpiryDate </td>
			<td style="text-align:center"> Date </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 2032-01-15  </td>
			<td> The expiry date of the document in question </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> documentIssueAuthority </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b>true </td>
			<td style="text-align:center">migration office  </td>
			<td> An authority that issued the document. </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> documentIssueCountry </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> LT </td>
			<td> A country that issued the document </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> documentIssueDate </td>
			<td style="text-align:center"> Date </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> 2022-01-15  </td>
			<td>Issue date of the document in question </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> documentNumber </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b> true </td>
			<td style="text-align:center"> 0123456789 </td>
			<td> Number of document in question </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> entityType </td>
			<td style="text-align:center"> <b>ENUM</b></br> [INDIVIDUAL, </br> ORGANIZATION] </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> INDIVIDUAL </td>
			<td> Entity type describes client status </td>
	</tr>
	<<tr>
			<td style="text-align:center"> <b> identityDocumentType </td>
			<td style="text-align:center"> <b>ENUM</b></br>[PASSPORT, </br> IDENTITYCARD,</br> RESIDENCEPERMIT,</br> DRIVINGLICENSE,</br> REGISTRATIONCERTIFICATE,</br> OTHER] </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> PASSPORT </td>
			<td> Identification document </td>
	</tr>
	</tbody>

</table>


## CountryOfTaxPaymentApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td> <b> country </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b>true </td>
			<td style="text-align:center"> LT </td>
			<td> Country of tax payment </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> taxpayerNumber </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 5541245574 </td>
			<td> The number of tax payer </td>
	</tr>
	</tbody>
</table>

## DeclaredTurnoverApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> from </td>
			<td style="text-align:center"> BigInteger </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> 1000 </td>
			<td> Amount range from.
At least one value (<From> or <To>)  must be specified </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> to </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> 5000 </td>
			<td> Amount to.
At least one value (<From> or <To>)  must be specified </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> turnoverRange </td>
			<td style="text-align:center"><b> ENUM </b></br> [SINGLE,</br> DAILY, </br> MONTHLY,</br> ANNUAL]  </td>
			<td style="text-align:center"><b> true </td>
			<td style="text-align:center"> MONTHLY </td>
			<td> Range of declared turnover </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> turnoverType </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"><b>true </td>
			<td style="text-align:center"> TURNOVER_PER_MONTH </td>
			<td> Type of declared turnover. Classifier turnoverType </td>
	</tr>
	</tbody>
</table>

## IncomeSourceApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> from </td>
			<td style="text-align:center"> BigInteger </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 100 </td>
			<td> Amount from </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> incomePercentage </td>
			<td style="text-align:center"> BigInteger </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 5 </td>
			<td> Percentage of income from the source </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> incomeSourceType </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b> true </td>
			<td style="text-align:center"> SALARY </td>
			<td> Type of income source. Classifier incomeSourceType </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> to </td>
			<td style="text-align:center"> BigInteger </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 1000 </td>
			<td> Amount to </td>
	</tr>
	</tbody>
</table>


## PaymentPurposeApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> paymentPurposeType </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b> true </td>
			<td style="text-align:center"> TAXES </td>
			<td> Type of income source, code of paymentPurposeType classifier </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> turnoverDirection </td>
			<td style="text-align:center"> <b> ENUM </b> </br> [INCOMING,</br>OUTGOING] </td>
			<td style="text-align:center"> <b> true </td>
			<td style="text-align:center"> OUT </td>
			<td> The turnover direction of payment </td>
	</tr>
	</tbody>
</table>

## SourceOfWealthApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> amount </td>
			<td style="text-align:center"> BigDecimal </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 100000 </td>
			<td> Collected monetary amount </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> code </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true </td>
			<td style="text-align:center"> INHERITANCE </td>
			<td> source of wealth type classifier </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> comment </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center">  </td>
			<td> Additional details about the source of wealth </td>
	</tr>
	</tbody>
</table>                 

## RelatedEntityApi

<table>
	<thead>
		<tr>
			<td style="text-align:center"> <b> field </td>
			<td style="text-align:center"> <b> type </td>
			<td style="text-align:center"> <b> mandatory </td>
			<td style="text-align:center"> <b> example </td>
			<td style="text-align:center"> <b> description </td>
		</tr>
	</thead>
	<tbody>
	<tr>
			<td style="text-align:center"> <b> relationType </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> <b> true </td>
			<td style="text-align:center"> OWNER </td>
			<td> Type of relationship between entities. RelationType classifier </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> share </td>
			<td style="text-align:center"> BigInteger </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 75 </td>
			<td> Shares owned by shareholders in the organization of the business entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> votePercentage </td>
			<td style="text-align:center"> BigInteger </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 99 </td>
			<td> Vote percentage of shareholders in the organization of business entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> activityDescription  </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> financial activity  </td>
			<td> Activity description of the related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> birthCountry </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT </td>
			<td> The birth country of the related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> birthDate </td>
			<td style="text-align:center"> Date </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 2000-05-28 </td>
			<td> Birth date of a related individual entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> country </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT </td>
			<td> Country of the related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> countryOfBusinessOperations </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT </td>
			<td> Country of Business Operations of the related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> entityType </td>
			<td style="text-align:center">  <b>ENUM</b></br> [INDIVIDUAL, </br>ORGANIZATION] </td>
			<td style="text-align:center"> <b>true </td>
			<td style="text-align:center"> INDIVIDUAL </td>
			<td> Entity type describes client status </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> establishmentDate </td>
			<td style="text-align:center"> Date </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 2020-05-30 </td>
			<td> Establishment date of related organization entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> extId </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 12345678912345 </td>
			<td> Used for screening callbacks to identify entity  </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> firstName </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> John </td>
			<td> First name of related entity br><b>Mandatory</b> when entityType = INDIVIDUAL </br><b>Not Used</b>  when entityType = ORGANIZATION </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> isInAdverseMedia </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> An indication of the existence of information for an adverse media entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> isPEP </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> An indicator for a related individual entity is a politically exposed person </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> isSanctioned </td>
			<td style="text-align:center"> Boolean </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> false </td>
			<td> Indicator for sanctions applied to the entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> lastName </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/false </td>
			<td style="text-align:center"> Rodriguez </td>
			<td> Last name of related entity </br><b>Mandatory</b> when entityType = INDIVIDUAL </br><b>Not Used</b>  when entityType = ORGANIZATION </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> legalForm </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> COOPERATIVE </td>
			<td> Legal form of organization </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> nationalCode </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> 123456789 </td>
			<td> National code or national identification number of individual or organization. If a country does not issue national code, any other unique identifier can be used </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> regionOfActivityDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> EU </td>
			<td> Description of activity region of related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> registrationCountry </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> LT </td>
			<td> Country of registration of related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> relationDescription </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> founder </td>
			<td> Description of the relationship between entities </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> title </td>
			<td style="text-align:center"> String </td>
			<td style="text-align:center"> true/ false </td>
			<td style="text-align:center"> Beko </td>
			<td> </br><b>Mandatory</b> when entityType = INDIVIDUAL </br><b>Not Used</b>  when entityType = ORGANIZATION </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> listActivity </td>
			<td style="text-align:center"> [ActivityApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of activities of related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> listAdditionalValues </td>
			<td style="text-align:center"> [AdditionalValueApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> Additional information about businessEntity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> listAddress </td>
			<td style="text-align:center"> [AddressApi]  </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of addresses </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> listBusinessEntityDocument </td>
			<td style="text-align:center"> [BusinessEntityDocumentApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of related entity document </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> listContact </td>
			<td style="text-align:center"> [ContactApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of contacts of related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> listCountryOfActivity </td>
			<td style="text-align:center"> [countryOfActivity] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of activity countries of related entity </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> listIncomeSource </td>
			<td style="text-align:center"> [IncomeSourceApi] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of income sources </td>
	</tr>
	<tr>
			<td style="text-align:center"> <b> listRegionOfActivity </td>
			<td style="text-align:center"> [regionOfActivity] </td>
			<td style="text-align:center"> false </td>
			<td style="text-align:center"> - </td>
			<td> List of activity regions of related entity </td>
	</tr>
	</tbody>
</table>

