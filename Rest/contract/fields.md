# CONTRACT Fields 

**Samples**

* [Load contract](./samples/loanContract.json)

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
			<td>financial_institution</td>
			<td>Name of the system requesting web service</td>
		</tr>
		<tr>
			<td><b>action</b></td>
			<td>String<br/><b>ENUM</b><br/>[CREATE (<i>default</i>), <br/> UPDATE]</td>
			<td>false</td>
			<td>CREATE</td>
			<td>
                <div>🚨<b>Alert:</b> Field omitted in single request.</div><br/>
                Element is used to create/update data of the contract.
            </td>
		</tr>
        <tr>
			<td><b>contractStatus</b></td>
			<td>String<br/><b>ENUM</b><br/>[ACTIVE, <br/> CLOSED]</td>
			<td>true</td>
			<td>ACTIVE</td>
			<td>
                A contract status.
            </td>
		</tr>
		<tr>
			<td><b>contractType</b></td>
			<td>
                String <br/>
                <a href="../../Classifiers/classifiers.md">(Contract type classifier)</a>
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
			<td>false</td>
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
                <a href="../../Classifiers/classifiers.md">(Business unit classifier)</a>
            </td>
			<td>true/false</td>
			<td>BUSINESS_UNIT_NAME</td>
			<td>This parameter is mandatory only for clients utilizing a multi-organizational solution. 
            ❗<b>Omit this parameter unless instructed about it.</b>❗<br/> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data. Each business unit can have its own set of users, permissions, and data access rules. <br/><i>(Upcoming feature)</i></td>
		</tr>
		<tr>
			<td><b>startAt</b></td>
			<td>Date</td>
			<td>false</td>
			<td>2000-01-03</td>
			<td>Contract start date or any other date that covers starting point</td>
		</tr>
		<tr>
			<td><b>endAt</b></td>
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
