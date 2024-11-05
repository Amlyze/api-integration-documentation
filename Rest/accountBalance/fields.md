# Account balance fields 

**Samples**

* [Daily balance](./samples/dailyBalance.json)

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
			<td><b>balanceType</b></td>
			<td>
                String <br/>
                <a href="../../Classifiers/classifiers.md">(Account balance type classifier)</a>
            </td>
			<td>true</td>
			<td>DAILY_BALANCE</td>
			<td>Type of balance type.</td>
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
            ❗<b>Omit this parameter unless instructed about it.</b>❗<br/> It serves to specify the unique identifier for the business unit. Business units are logical groupings of users and data.</td>
		</tr>
		<tr>
			<td><b>balanceAt</b></td>
			<td>Timestamp<br/>RFC 3339 (ISO 8601)</td>
			<td>false</td>
			<td>2024-05-26T16:49:50.237</td>
			<td>Balance datetime.</td>
		</tr>
		<tr>
			<td><b>value</b></td>
			<td>BigDecimal</td>
			<td>true</td>
			<td>100000.5665</td>
			<td>Balance value.</td>
		</tr>
        <tr>
			<td><b>equivalentValue</b></td>
			<td>BigDecimal</td>
			<td>false</td>
			<td>33333.5665</td>
			<td>Equivalent balance value.</td>
		</tr>
	</tbody>
</table>

