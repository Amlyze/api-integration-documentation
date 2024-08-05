# Contract registration (coming soon❗)

This section provides detailed information on the endpoints that can be used to create and manage contracts. Contracts can be any type of documents with custom set of fields/elements.


----

## EndPoints

*swagger UI*  `GET / swagger-ui/`

Create contract `POST /amlyze-ws-rest/contract (application/json)`

Update contract `PUT /amlyze-ws-rest/contract (application/json)`

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md)

## Samples

* [contract_loan](samples/contractLoan.json)

---

## Responses

<table>
    <thead>
        <tr>
            <td><b>Code</b></td>
            <td><b>Status</b></td>
            <td><b>Response</b></td>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><b>200</b></td>
            <td><i>OK</i></td>
            <td>
                <pre>
{
    "resultType": "REQUEST_ACCEPTED"
}
                </pre>
            </td>
        </tr>
        <tr>
            <td><b>400</b></td>
            <td><i>Bad Request</i></td>
            <td> 
                <pre>
{
    "errors": ["extId is mandatory"]
}
                </pre>
            </td>
        </tr>
        <tr>
            <td><b>404</b></td>
            <td><i>Not Found</i></td>
            <td>
                <pre>
{
    "timestamp": "2023-09-08T05:55:12.219+00:00",
    "status": 404,
    "error": "Not Found",
    "path": "/amlyze-ws-rest/contract"
}
                </pre>
            </td>
        </tr>
        <tr>
            <td><b>500</b></td>
            <td><i>Internal Server Error</i></td>
            <td> 
                <pre>
{
    "resultType": "REQUEST_REJECTED",
    "errorDescription": "duplicate communicationNumber"
}
                </pre>
            </td>
        </tr>
    </tbody>
</table>

----
**Possible errors**

All possible errors can be found [*here*](possibleErrors.md)  


----

## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully add an account. Other fields may be optionally included, as specified in the API documentation which that can be found [*here*](fields.md).

```json
{
    "communicationNumber": "COM216a",
    "requester": "financial_institution",
    "classifierType": "LOAN",
    "extId": "any_contract_1232",
    "documentCode": "REG74121101"
  }
```


