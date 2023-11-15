# Account Registration

This section provides detailed information on the endpoints that can be used to create and manage accounts. Accounts are used to uniquely identify customers in operation parties.


----

## EndPoints

*swagger UI*  `GET / swagger-ui/`

`POST /amlyze-ws-rest/account (application/json)`

The request body contains the data that you are sending to the API. The data documentation can be found [*here*](fields.md)

## Samples

* [account_active](samples/account_active.json)
* [account_suspended](samples/account_suspended.json)
* [account_closed](samples/account_closed.json)
* [account_minimalistic](samples/account_minimalistic.json)

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
    "errors": ["entityType is mandatory"]
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
    "path": "/amlyze-ws-rest/operationn"
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

All possible errors can be found [*here*](acc_possible_errors.md)  


----

## Minimalistic request

The Minimalistic request example below shows the minimum required fields to successfully add an account. Other fields may be optionally included, as specified in the API documentation which that can be found [*here*](fields.md).

```json
{
  "communicationNumber": "Com_1545",
  "requester": "financial_institution",
  "accountExtId": "Ext87887",
  "accountNumber": "LI9208800274335945522",
  "accountStatus": "ACTIVE",
  "bic": "VABAL22",
  "businessEntityExtId": "ExtId_6565",
  "currencyCode": "EUR",
  "isOtherFinInstAccount": true,
  "openingDate": "2023-09-05T08:07:34.605Z"
}
```


