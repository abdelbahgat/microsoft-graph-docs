---
title: "Close Session"
description: "Use this API to close an existing workbook session. "
author: "lumine2008"
ms.localizationpriority: medium
ms.prod: "excel"
doc_type: apiPageType
---

# Close Session

Namespace: microsoft.graph

Use this API to close an existing workbook session.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Files.ReadWrite    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /me/drive/items/{id}/workbook/closeSession
POST /me/drive/root:/{item-path}:/workbook/closeSession
workbook-session-id: {session-id}
```
## Request headers
| Name                | Description                      |
|:--------------------|:---------------------------------|
| Authorization       | Bearer {token}. Required.        |
| workbook-session-id | Workbook session Id to be closed |

## Request body
This API does not require any request body.

## Response

If successful, this method returns `204 No Content` response code.

## Example
##### Request
Here is an example of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "close_workbook_session"
}-->
```http
POST https://graph.microsoft.com/v1.0/me/drive/items/{id}/workbook/closeSession
Content-type: application/json
workbook-session-id: {session-id}

{

}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/close-workbook-session-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/close-workbook-session-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/close-workbook-session-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/close-workbook-session-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/close-workbook-session-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

Note that workbook-session-id header is required.


##### Response
Here is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 204 No Content
```

<!-- {
  "type": "#page.annotation",
  "suppressions": [
  ]
}-->

