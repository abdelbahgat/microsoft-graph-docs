---
title: "Delete bookingBusiness"
description: "Delete a bookingBusiness object."
ms.localizationpriority: medium
author: "arvindmicrosoft"
ms.prod: "bookings"
doc_type: apiPageType
---

# Delete bookingBusiness

Namespace: microsoft.graph

Delete a [bookingBusiness](../resources/bookingbusiness.md) object.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "bookingbusiness_delete" } -->
[!INCLUDE [permissions-table](../includes/permissions/bookingbusiness-delete-permissions.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
DELETE /solutions/bookingBusinesses/{id}

```
## Request headers
| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer {code}|

## Request body
Don't supply a request body for this method.


## Response
If successful, this method returns a `204 No Content` response code. It doesn't return anything in the response body.

## Example
### Request
Here's an example of the request.

<!-- {
  "blockType": "request",
  "sampleKeys": ["fabrikam@contoso.onmicrosoft.com"]
}-->
```http
DELETE https://graph.microsoft.com/v1.0/solutions/bookingBusinesses/fabrikam@contoso.onmicrosoft.com
```

### Response
Here's an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 204 No Content
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Delete bookingBusiness",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->


