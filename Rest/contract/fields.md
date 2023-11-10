# CONTRACT Fields 

<table>
	<thead>
		<tr>
			<td><b> field </b></td>
			<td><b> type </b></td>
			<td><b> mandatory </b></td>
			<td><b> example </b></td>
			<td  width:600px><b> description </b></td>
		</tr>
	</thead>
	<tbody>
		<tr>
			<td><b> communicationNumber </b></td>
			<td> String </td>
			<td><b> true </b></td>
			<td> ComNr_000321 </td>
			<td> Unique number of communication. used for risk assessment callback </td>
		</tr>
		<tr>
			<td><b> requester </b></td>
			<td> String </td>
			<td><b> true </b></td>
			<td> ComNr_000321 </td>
			<td> Name of the system requesting web service </td>
		</tr>
		<tr>
			<td><b> action </b></td>
			<td> <b>ENUM</b> <br/>[CREATE (<i>default</i>), <br/> UPDATE] </td>
			<td> false </td>
			<td> CREATE </td>
			<td> Element is used to change the data of an existing Contract. </br>❗ NOTE: all data will be replaced with newly received ones </td>
		</tr>
		<tr>
			<td><b> contractType </b></td>
			<td> <b> CLASSIFIER </b><br>String </td>
			<td><b> true </b></td>
			<td>LOAN_CONTRACT</td>
			<td>Type of contract for evaluation of the object.<br>💡 Possible values will be updated during configuration period. <br>💡 [AdditionalProperty] fields should be validated against classifier.</td>
		</tr>
		<tr>
			<td><b> extId </b></td>
			<td> String </td>
			<td><b> true </b></td>
			<td> any_contract_1232 </td>
			<td> Unique external contract identifier. The identifier corresponds to the contract identifier in the financial institution </td>
		</tr>
		<tr>
			<td><b> contractCode </b></td>
			<td> String </td>
			<td><b> true </b></td>
			<td> REG74121101 </td>
			<td> Contract code or number </td>
		</tr>
		<tr>
			<td><b> customerExtId </b></td>
			<td> String </td>
			<td>false </td>
			<td> cust_1232</td>
			<td> External customer identifier. The identifier corresponds to the client's identifier in the financial institution </td>
		</tr>
        <tr>
            <td ><b> accountExtId </b></td>
            <td > String </td>
            <td > false </td>
            <td > Acc_0011  </td>
            <td> External account identification number. Corresponds to the account's identifier in the financial institution </td>
        </tr>
        <tr>
            <td ><b> businessUnit </b></td>
            <td > String </td>
            <td > false </td>
            <td > DEFAULT </td>
            <td> Business unit code where contract was signed.❗NOTE: If exists more than one business unit then this field is mandatory. In other case default value will be used. </td>
        </tr>
		<tr>
			<td><b> startDate </b></td>
			<td> Date </td>
			<td> false </td>
			<td> 2000-01-03 </td>
			<td> Contract start date or any other date that covers starting point </td>
		</tr>
		<tr>
			<td><b> endDate </b></td>
			<td> Date </td>
			<td> false </td>
			<td> 1995-05-24 </td>
			<td> Contract end date or any other date that covers ending point </td>
		</tr>
		<tr>
			<td ><b> additionalProperties  </b></td>
			<td > [AdditionalProperty] </td>
			<td > false </td>
			<td > - </td>
			<td> Additional properties for contract. </td>
		</tr>
	</tbody>
</table>

## AdditionalProperty

<table>
	<thead>
		<tr>
			<td > <b> field </b></td>
			<td > <b> type </b></td>
            <td > <b> mandatory </b></td>
			<td > <b> example </b></td>
			<td > <b> description </b></td>
		</tr>
	</thead>
	<tbody>
	    <tr>
	    		<td > <b> code </b></td>
	    		<td > String </td>
                <td > <b>true </b></td>
	    		<td > 'interest' | 'agency' | 'status' | 'principal_amount' </td>
	    		<td> Unique code </td>
	    </tr>
	    <tr>
	    		<td > <b> title </b></td>
	    		<td > String </td>
                <td > <b>true </b></td>
	    		<td > Human readable title. </td>
	    		<td>  Description, what kind of data is stored here </td>
	    </tr>
	    <tr>
	    		<td > <b> value </b></td>
	    		<td > String </td>
                <td > false </td>
	    		<td > 10000 </td>
	    		<td> value of field </td>
	    </tr>
	    <tr>
	    		<td > <b> dataType </b></td>
	    		<td > <b>ENUM </b></br>[STRING,</br> INTEGER,</br> DECIMAL,</br> DATE,</br> TIMESTAMP,</br> BOOLEAN,</br> EXTERNAL_LINK] </td>
                <td > false </td>
	    		<td > STRING </td>
	    		<td> Default 'STRING' </td>
	    </tr>
	</tbody>
	
</table>

		

