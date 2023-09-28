# Account Registration

This section provides detailed information on the endpoints that can be used to create and manage accounts. Accounts are used to uniquely identify customers in operation parties.


----

## EndPoints

*swagger*  `GET / swagger-ui/`

`POST /amlyze-ws//ImportAccountV2Service (text/xml)`

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md)

## Samples

* [account_Active.json](samples/account_Active.xml)
* [account_Suspended.json](samples/account_Suspended.xml)
* [account_Closed.json](samples/account_Closed.xml)
* [account_Minimalistic.json](samples/account_Minimalistic.xml)
---

## Responses



<table>
		<thead>
			<tr>
				<td style="text-align:center"><b>Code<b></td>
				<td style="text-align:center"><b>Status<b></td>
				<td style="text-align:center"><b>Response<b></td>
			</tr>
		</thead>
		<tbody>
			<tr>
				<td><b>200<b></td>
				<td style="text-align:center"><i>OK<i></td>
				<td>
					<pre>
						<code>
&lt;ns2:ResultType&gt;OK&lt;/ns2:ResultType&gt;
						</code>
					</pre>	
				</td>
			</tr>
			<tr>
				<td><b>200<b></td>
				<td style="text-align:center"><i>OK<i></td>
				<td>
      				<pre>
						<code>
&lt;ns2:ResultType&gt;ERROR&lt;/ns2:ResultType&gt;
&lt;ns2:ErrorCode&gt;001&lt;/ns2:ErrorCode&gt;
&lt;ns2:ErrorDescription&gt;Currency does not exist in Amlyze&lt;/ns2:ErrorDescription&gt;
						</code>
    				 </pre>
   				 </td>
			</tr>
			<tr>	
				<td><b>400<b></td>
				<td style="text-align:center"><i>Bad Request<i></td>
				<td>
				 <pre>
				 	<code>
					-
					</code>
				</pre>		
				</td>
			</tr>
				<td style="text-align:center"><b>404<b></td>
				<td style="text-align:center">Not Found</td>
				<td>
				 <pre>
				 	<code>
					-
					</code>
				</pre>		
				</td>
			</tr>
			<tr>
				<td><b>500<b></td>
				<td style="text-align:center"><i>Internal Server Error<i></td>
				<td>
				 <pre>
				 	<code>
       &lt;faultstring xml:lang=&quot;en&quot;&gt;Validation error&lt;/faultstring&gt;
            &lt;detail&gt;
                &lt;spring-ws:ValidationError xmlns:spring-ws=&quot;http://springframework.org/spring-ws&quot;&gt;cvc-datatype-valid.1.2.1: 'truee' is not a valid value for 'boolean'.&lt;/spring-ws:ValidationError&gt;
                &lt;spring-ws:ValidationError xmlns:spring-ws=&quot;http://springframework.org/spring-ws&quot;&gt;cvc-type.3.1.3: The value 'truee' of element 'isOtherFinInstAccount' is not valid.&lt;/spring-ws:ValidationError&gt;
            &lt;/detail&gt;
    				 </code>
				</pre>		
				</td>
			</tr>
		</tbody>	
</table>

----
**Possible errorrs**

All possible errors can be found [*here*](acc_possible_errors.md)  


----

## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully add an account. Other fields may be optionally included, as specified in the API documentation which that can be found [*here*](fields.md).

```xml
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
    <soap:Body>
        <AMLYZE_ACCOUNT xmlns="urn:amlyze-services:ImportAccountService_v1r0">
            <CommunicationNumber>ComNr_{{seq}}</CommunicationNumber>
            <Requester>Financial_Bank</Requester>
            <ListAccount>
                <Account>
                    <BusinessEntityExtId>Cust_1145</BusinessEntityExtId>
                    <AccountExtId>Extid_004</AccountExtId>
                    <AccountNumber>LT5630800200000011112</AccountNumber>
                    <CurrencyCode>EUR</CurrencyCode>
                    <isOtherFinInstAccount>true</isOtherFinInstAccount>
                    <BIC>CRYPXX</BIC>
                    <OpeningDate>2023-09-16T12:10:11+02:00</OpeningDate>
                    <AccountStatus>ACTIVE</AccountStatus> 
                </Account>
            </ListAccount>
        </AMLYZE_ACCOUNT>
    </soap:Body>
</soap:Envelope>
```


