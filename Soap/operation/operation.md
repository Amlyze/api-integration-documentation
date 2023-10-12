# Operations

An operation is a transaction between two or more parties, where one of the parties is always the customer. The other party(ies) are called counterparties. The documentation provides information on the endpoints, responses, and possible errors for API requests for operations. It also includes minimalistic request examples.

---
## EndPoint

**swagger** `GET /swagger-ui/`

**URL structure:** `http://[host][port][path][service]`

**Example:** `http://[host]:8878/amlyze-ws/EvaluateOperationV2Service

---

## Additional Info

* METHOD ` POST ` 
* Auth required: `NO`
* Content-Type: `text/xml`
---

## EndPoints

*swagger UI*  `GET / swagger-ui/`

`POST /amlyze-ws/EvaluateOperationV2Service (text/xml)`


## Samples


[<b>SEPA Fields</b>](SEPA/SEPA_Fields.md)
* [Evaluate_SEPA_Full.json](SEPA/SEPA_Samples/evaluate_SEPA_Full.xml)
* [Evaluate_SEPA_Mandatory.json](SEPA/SEPA_Samples/evaluate_SEPA_Mandatory.xml)
* [Import_SEPA_Full.json](SEPA/SEPA_Samples/import_SEPA_Full.xml)
* [Import_SEPA_Mandatory.json](SEPA/SEPA_Samples/import_SEPA_Mandatory.xml)
---

[<b>SWIFT Fields</b>](SWIFT/SWIFT_Fields.md)
* [Evaluate_SWIFT_Full.json](SWIFT/SWIFT_Samples/evaluate_SWIFT_Full.xml)
* [Evaluate_SWIFT_Mandatory.json](SWIFT/SWIFT_Samples/evaluate_SWIFT_Mandatory.xml)
* [Import_SWIFT_Full.json](SWIFT/SWIFT_Samples/import_SWIFT_Full.xml)
* [Import_SWIFT_Mandatory.json](SWIFT/SWIFT_Samples/import_SWIFT_Mandatory.xml)
---

[<b>PIS Fields</b>](PIS/PIS_Fields.md)
* [Evaluate_PIS_Full.json](PIS/PIS_Samples/evaluate_PIS_Full.xml)
* [Evaluate_PIS_Mandatory.json](PIS/PIS_Samples/evaluate_PIS_Mandatory.xml)
* [Import_PIS_Full.json](PIS/PIS_Samples/import_PIS_Full.xml)
* [Import_PIS_Mandatory.json](PIS/PIS_Samples/import_PIS_Mandatory.xml)
---

[<b>INTERNAL Fields</b>](INTERNAL/INTERNAL_Fields.md)
* [Evaluate_INTERNAL_Full.json](INTERNAL/INTERNAL_Samples/evaluate_INTERNAL_Full.xml)
* [Evaluate_INTERNAL_Mandatory.json](INTERNAL/INTERNAL_Samples/evaluate_INTERNAL_Mandatory.xml)
* [Import_INTERNAL_Full.json](INTERNAL/INTERNAL_Samples/import_INTERNAL_Full.xml)
* [Import_INTERNAL_Mandatory.json](INTERNAL/INTERNAL_Samples/import_INTERNAL_Mandatory.xml)
---

[<b>CARD_PAYMENT Fields</b>](CARD_PAYMENT/CARD_PAYMENT_Fields.md)
* [Evaluate_CARD_PAYMENT_Full.json](samples/evaluate_CARD_PAYMENT_Full.xml)
* [Evaluate_CARD_PAYMENT_Mandatory.json](samples/evaluate_CARD_PAYMENT_Mandatory.xml)
* [Import_CARD_PAYMENT_Full.json](samples/import_CARD_PAYMENT_Full.xml)
* [Import_CARD_PAYMENT_Mandatory.json](samples/import_CARD_PAYMENT_Mandatory.xml)
---

[<b>CARD_CASH Fields</b>](CARD_CASH/CARD_CASH_Fields.md)
* [Evaluate_CARD_CASH_Full.json](CARD_CASH/CARD_CASH_Samples/evaluate_CARD_PAYMENT_Full.xml)
* [Evaluate_CARD_CASH_Mandatory.json](CARD_CASH/CARD_CASH_Samples/evaluate_CARD_CASH_Mandatory.xml)
* [Import_CARD_CASH_Full.json](CARD_CASH/CARD_CASH_Samples/import_CARD_CASH_Full.xml)
* [Import_CARD_CASH_Mandatory.json](CARD_CASH/CARD_CASH_Samples/import_CARD_CASH_Mandatory.xml)
---

[<b>FASTER_PAYMENTS Fields</b>](FASTER_PAYMENTS/FASTER_PAYMENTS_Fields.md)
* [Evaluate_FASTER_PAYMENTS_Full.json](FASTER_PAYMENTS/FASTER_PAYMENTS_Samples/evaluate_FASTER_PAYMENTS_Full.xml)
* [Evaluate_FASTER_PAYMENTS_Mandatory.json](FASTER_PAYMENTS/FASTER_PAYMENTS_Samples/evaluate_FASTER_PAYMENTS_Mandatory.xml)
* [Import_FASTER_PAYMENTS_Full.json](FASTER_PAYMENTS/FASTER_PAYMENTS_Samples/import_FASTER_PAYMENTS_Full.xml)
* [Import_FASTER_PAYMENTS_Mandatory.json](FASTER_PAYMENTS/FASTER_PAYMENTS_Samples/import_FASTER_PAYMENTS_Mandatory.xml)
---

[<b>CRYPTO Fields</b>](CRYPTO/CRYPTO_Fields.md)
* [Evaluate_CRYPTO_Full.json](CRYPTO/CRYPTO_Samples/evaluate_CRYPTO_Full.xml)
* [Evaluate_CRYPTO_Mandatory.json](CRYPTO/CRYPTO_Samples/evaluate_CRYPTO_Mandatory.xml)
* [Import_CRYPTO_Full.json](CRYPTO/CRYPTO_Samples/import_CRYPTO_Full.xml)
* [Import_CRYPTO_Mandatory.json](CRYPTO/CRYPTO_Samples/import_CRYPTO_Mandatory.xml)
---

[<b>CRYPTO_EXCHANGE Fields</b>](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Fields.md)
* [Evaluate_CRYPTO_EXCHANGE_Full.json](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Samples/evaluate_CRYPTO_EXCHANGE_Full.xml)
* [Evaluate_CRYPTO_EXCHANGE_Mandatory.json](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Samples/evaluate_CRYPTO_EXCHANGE_Mandatory.xml)
* [Import_CRYPTO_EXCHANGE_Full.json](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Samples/import_CRYPTO_EXCHANGE_Full.xml)
* [Import_CRYPTO_EXCHANGE_Mandatory.json](CRYPTO_EXCHANGE/CRYPTO_EXCHANGE_Samples/import_CRYPTO_EXCHANGE_Mandatory.xml)
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
&lt;ns2:ResultType&gt;REQUEST_ACCEPTED&lt;/ns2:ResultType&gt;
&lt;ns2:CommunicationStatus&gt;COMPLETED&lt;/ns2:CommunicationStatus&gt;
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
&lt;ns2:ResultType&gt;REQUEST_REJECTED&lt;/ns2:ResultType&gt;
&lt;ns2:CommunicationStatus&gt;INVALID&lt;/ns2:CommunicationStatus&gt;
&lt;ns2:ErrorCode&gt;O006.Ot02.Op04&lt;/ns2:ErrorCode&gt;
&lt;ns2:ErrorDescription&gt;Error: Problem with OperationType.  Problem with OperationParties.  No operation party account related to your institution BIC, or Customer&lt;/ns2:ErrorDescription&gt;
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
			<tr>
				<td><b>500<b></td>
				<td style="text-align:center"><i>Internal Server Error<i></td>
				<td>
      				<pre>
						<code>
&lt;faultstring xml:lang=&quot;en&quot;&gt;Validation error&lt;/faultstring&gt;
&lt;detail&gt;
&lt;spring-ws:ValidationError xmlns:spring-ws=&quot;http://springframework.org/spring-ws&quot;&gt;cvc-complex-type.2.4.b: The content of element 'OperationParty' is not complete. One of '{&quot;urn:amlyze-services:EvaluateOperationService_v2r0&quot;:ELEMENT}' is expected.&lt;/spring-ws:ValidationError&gt;
&lt;/detail&gt;
						</code>
    				 </pre>
   				 </td>
			</tr>
		</tbody>
</table>


**Possible errorrs**

All possible errors can be found [*here*](op_possible_errors.md)  


------

## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully create an operation. Other fields may be optionally included, as specified in the API documentation.

```xml
<?xml version="1.0" encoding="utf-8"?>
<soap:Envelope xmlns:soap="http://schemas.xmlsoap.org/soap/envelope/">
    <soap:Body>
        <AMLYZE_OPERATION xmlns="urn:amlyze-services:EvaluateOperationService_v2r0">
            <CommunicationNumber>ComNr_145</CommunicationNumber>
            <Requester>BankBank</Requester>
            <RiskManagementCategory>OP_PK</RiskManagementCategory>
            <SourceOfRiskLevel>EVALUATE</SourceOfRiskLevel>
            <OperationExtId>Ext_145</OperationExtId>
            <OperationType>SEPA</OperationType>
            <FinancialFlowDirection>OUTGOING</FinancialFlowDirection>
            <OperationDateTime>2023-02-23T15:09:33+02:00</OperationDateTime>
            <Currency>EUR</Currency>
            <Amount>50</Amount>
            <Description>Fund Transfer</Description>
            <ListOperationParty>
                <OperationParty>
                    <PartyRole>DEBTOR</PartyRole>
                    <AccountNumber>CY58625315343982956814247917</AccountNumber>
                    <Currency>EUR</Currency>
                    <BIC>BARCGB22</BIC>
                    <EntityType>ORGANIZATION</EntityType>
                    <Title>Baidu</Title>
                </OperationParty>
                <OperationParty>
                    <PartyRole>CREDITOR</PartyRole>
                    <AccountNumber>FI7731184218934256</AccountNumber>
                    <EntityType>ORGANIZATION</EntityType>
                    <Title>BrotherHood</Title>
                </OperationParty>
            </ListOperationParty>
        </AMLYZE_OPERATION>
    </soap:Body>
</soap:Envelope>
```
```
