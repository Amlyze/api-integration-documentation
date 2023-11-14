# CONTRACT Fields 

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
			<td>Unique number of communication. used for risk assessment callback</td>
		</tr>
		<tr>
			<td><b>requester</b></td>
			<td>String</td>
			<td>true</td>
			<td>ComNr_000321</td>
			<td>Name of the system requesting web service</td>
		</tr>
		<tr>
			<td><b>contractType</b></td>
			<td>
                String <br/>
                <a href="../README.md#classifiers">(Contract type classifier)</a>
            </td>
			<td>true</td>
			<td>LOAN_CONTRACT</td>
			<td>Type of contract for evaluation of the object.<br/>💡 Possible values will be updated during configuration period. <br/>💡 [AdditionalProperty] fields should be validated against classifier.</td>
		</tr>
		<tr>
			<td><b>extId</b></td>
			<td>String</td>
			<td>true</td>
			<td>any_contract_1232</td>
			<td>Unique external contract identifier. The identifier corresponds to the contract identifier in the financial institution</td>
		</tr>
		<tr>
			<td><b>contractCode</b></td>
			<td>String</td>
			<td>true</td>
			<td>REG74121101</td>
			<td>Contract code or number</td>
		</tr>
		<tr>
			<td><b>customerExtId</b></td>
			<td>String</td>
			<td>false</td>
			<td>cust_1232</td>
			<td>External customer identifier. The identifier corresponds to the client's identifier in the financial institution</td>
		</tr>
        <tr>
            <td><b>accountExtId</b></td>
            <td>String</td>
            <td>false</td>
            <td>Acc_0011</td>
            <td>External account identification number. Corresponds to the account's identifier in the financial institution</td>
        </tr>
		<tr>
			<td><b>businessUnit</b></td>
			<td>
                String <br/>
                <a href="../README.md#classifiers">(Business unit classifier)</a>
            </td>
			<td>true/false</td>
			<td>BUSINESS_UNIT_NAME</td>
			<td>
                Unit data identification for controllability/observability.
                <br/>❗NOTE: parameter is required only if business unit strict mode enabled
            </td>
		</tr>
		<tr>
			<td><b>startDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2000-01-03</td>
			<td>Contract start date or any other date that covers starting point</td>
		</tr>
		<tr>
			<td><b>endDate</b></td>
			<td>Date</td>
			<td>false</td>
			<td>1995-05-24</td>
			<td>Contract end date or any other date that covers ending point</td>
		</tr>
		<tr>
			<td><b>additionalProperties</b></td>
            <td><a href="#AdditionalProperty">[AdditionalProperty]</a></td>
			<td>false</td>
			<td>-</td>
			<td>Additional properties for contract.</td>
		</tr>
	</tbody>
</table>

## AdditionalProperty

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
            <td>'interest' | 'agency' | 'status' | 'principal_amount'</td>
            <td>Unique code</td>
	    </tr>
	    <tr>
            <td><b>title</b></td>
            <td>String</td>
            <td>true</td>
            <td>Human readable title.</td>
            <td> Description, what kind of data is stored here</td>
	    </tr>
	    <tr>
            <td><b>value</b></td>
            <td>String</td>
            <td>false</td>
            <td>10000</td>
            <td>value of field</td>
	    </tr>
	    <tr>
            <td><b>dataType</b></td>
            <td>String<br/><b>ENUM</b><br/>[STRING,<br/> INTEGER,<br/> DECIMAL,<br/> DATE,<br/> TIMESTAMP,<br/> BOOLEAN,<br/> EXTERNAL_LINK]</td>
            <td>false</td>
            <td>STRING</td>
            <td>Default 'STRING'</td>
	    </tr>
	</tbody>
</table>
