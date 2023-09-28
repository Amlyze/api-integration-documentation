# Possible Errors
<i>This section lists the possible errors that can occur when making a bad request to the API. A bad request is a request that somehow does not follow the API specifications.

<table>
		<thead>
			<tr>
				<td style="text-align:center"><b>Error Desctiption</td>
		</thead>
		<tbody>
			<tr>
				<td >CommunicationNumber is mandatory</td>
            <tr>
				<td>RiskManagementCategory is mandatory</td>
			</tr>
            <tr>
				<td >RiskManagementCategory does not exist in amlyze</td>
			</tr>
            <tr>
				<td>Requester is mandatory</td>
			</tr>
             <tr>
				<td>SourceOfRiskLevel is mandatory, allowed values: IMPORT / EVALUATE</td>
			</tr>
             <tr>
				<td>OperationExtId is mandatory</td>
			</tr>
             <tr>
				<td>OperationType is mandatory</td>
			</tr>
             <tr>
				<td>Problem with OperationType (INVALID).  INVALID is not defined in Amlyze. Check Operation type classifier for available values</td>
			</tr>
             <tr>
				<td>Currency is mandatory, check Currency classifier codes for alowed values</td>
			</tr>
             <tr>
				<td>Currency is mandatory, check Currency classifier codes for alowed values</td>
			</tr>
             <tr>
				<td>SourceCountry is mandatory, check country classifier codes for alowed values</td>
			</tr>
             <tr>
				<td>DestinationCountry is mandatory, check country classifier codes for alowed values</td>
			</tr>
            <tr>
				<td>Description is mandatory</td>
			</tr>
            <tr>
				<td>Problem with OperationType (SEPA).  Problem with OperationParties.  No operation party account related to your institution BIC, or Customer</td>
			</tr>
            <tr>
				<td>Invalid FinancialFlowDirection. Your institution CREDITOR found for OUTGOING operation</td>
			</tr>
            <tr>
				<td>Problem with OperationType (SEPA).  Problem with OperationParties.  Invalid count of your institution operation parties for SEPA operationType</td>
			</tr>
		</tbody>
</table>
