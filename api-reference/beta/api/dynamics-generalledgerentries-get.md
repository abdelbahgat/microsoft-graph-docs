---
title: Get generalLedgerEntries 
description: Gets a general ledger entry object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen
ms.localizationpriority: medium
ms.prod: "dynamics-365-business-central"
doc_type: apiPageType
---

# Get generalLedgerEntries

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the properties and relationships of a general ledger entry object for Dynamics 365 Business Central.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "dynamics_generalledgerentries_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/dynamics-generalledgerentries-get-permissions.md)]


## HTTP request
```
GET /financials/companies/{id}/generalLedgerEntries/{id}
```

## Optional query parameters
This method supports the [OData Query Parameters](/graph/query-parameters) to help customize the response.

## Request headers
|Header       |Value             |
|-------------|------------------|
|Authorization|Bearer. Required. |

## Request body
Don't supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and a **generalLedgerEntries** object in the response body.

## Example

**Request**

Here is an example of the request.
```http
GET https://graph.microsoft.com/beta/financials/companies/{id}/generalLedgerEntries/{id}
```

**Response**

Here is an example of the response. 

> **Note**: The response object shown here might be shortened for readability.

```json
{
    "id": "10700",
    "postingDate": "2017-03-15",
    "documentNumber": "108027",
    "documentType": "Invoice",
    "accountId": "id-value",
    "accountNumber": "7210",
    "description": "Order 106003",
    "debitAmount": 6943.8,
    "creditAmount": 0,
    "lastModifiedDateTime": "2017-03-15T02:20:58.747Z"
}
```



