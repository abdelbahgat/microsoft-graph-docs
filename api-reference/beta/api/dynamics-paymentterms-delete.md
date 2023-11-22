---
title: Delete paymentTerms 
description: Deletes a payment term object in Dynamics 365 Business Central.
services: project-madeira
documentationcenter: ''
author: SusanneWindfeldPedersen
ms.localizationpriority: medium
ms.prod: "dynamics-365-business-central"
doc_type: apiPageType
---

# Delete paymentTerms

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete a payment terms object from Dynamics 365 Business Central.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "dynamics_paymentterms_delete" } -->
[!INCLUDE [permissions-table](../includes/permissions/dynamics-paymentterms-delete-permissions.md)]

## HTTP request
```
DELETE /financials/companies/{id}/paymentTerms/{id}
```

## Optional query parameters
This method supports the [OData Query Parameters](/graph/query-parameters) to help customize the response.

## Request headers

|Header         |Value                     |
|---------------|--------------------------|
|Authorization  |Bearer {token}. Required. |
|If-Match       |Required. When this request header is included and the eTag provided doesn't match the current tag on the **paymentTerms**, the **paymentTerms** isn't updated. |

## Request body
Don't supply a request body for this method.

## Response
If successful, this method returns ```204 No Content``` response code. It doesn't return anything in the response body.

## Example

**Request**

Here's an example of the request.

```http
DELETE https://graph.microsoft.com/beta/financials/companies/{id}/paymentTerms/{id}
```

**Response** 

Here's an example of the response. 

```http
HTTP/1.1 204 No Content
```


