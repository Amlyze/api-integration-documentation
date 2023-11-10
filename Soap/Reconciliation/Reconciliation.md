# Intro

Reconciliation is a vital process that ensures the accuracy of your data. With the reconciliation URL, you can easily request and retrieve a list of information about:
* Customer
* Accounts
* Operations

---
# URL

URL with specified  {{Service}} and Parameters lets you retrieve needed information

Example

# Workflow

`Request -> Retrieve`

The request offers the ability to retrieve information about all or a particular number of items during a specificied time interval.

---
Service

Offers the ability to retrieve result items about:
* GET /reconciliation/customers
* GET /reconciliation/accounts
* GET /reconciliation/operations

# Parameters

You can use the query parameters below . The provided Query Parameters can be manipulated depending on the needed items to be retrieved

# Response

The retrieved information about the list items is shown in a Response part.
Based on requested {{Service}}  and provided Parameters   ⟶   response returns JSON  information such as :



## Respones Example


`
{
    "result": {
        "@type": "type.googleapis.com/customersreconciliation.v1.CustomersReconciliationResult",
        "list": [
            {
                "requestId": "ComNr_0a0022",
                "requestedAt": "2023-03-17T13:08:25Z",
                "status": "REQUEST_STATUS_SUCCESS",
                "externalId": "Id_Test_011a2"
            },
            {
                "requestId": "ComNr_00022",
                "requestedAt": "2023-03-17T13:08:18Z",
                "status": "REQUEST_STATUS_SUCCESS",
                "externalId": "Id_Test_0112"
            },
            {
                "requestId": "ComNr_011115999996954",
                "requestedAt": "2023-03-17T08:51:44Z",
                "status": "REQUEST_STATUS_SUCCESS",
                "externalId": "Id_011AAZZ"
            },
            {
                "requestId": "ComNr_0002.3",
                "requestedAt": "2023-03-16T20:51:06Z",
                "status": "REQUEST_STATUS_SUCCESS",
                "externalId": "ExtId_000.zzb25az3"
            },
            {
                "requestId": "ComNr_011115999997150",
                "requestedAt": "2023-03-14T13:04:11Z",
                "status": "REQUEST_STATUS_SUCCESS",
                "externalId": "Id_01100900xx"
            },
            {
                "requestId": "ComNr_011115999997161",
                "requestedAt": "2023-03-14T10:46:32Z",
                "status": "REQUEST_STATUS_SUCCESS",
                "externalId": "Id_01100900x"
            }
        ],
        "total": 6
    },
    "errors": []
}
`