---
title: "group: unsubscribeByMail"
description: "Calling this method will prevent the current user from receiving email notifications for this group about new posts, events, and files in that group. Supported for Microsoft 365 groups only. "
ms.localizationpriority: medium
author: "psaffaie"
ms.prod: "groups"
doc_type: apiPageType
---

# group: unsubscribeByMail

Namespace: microsoft.graph

Calling this method will prevent the current user from receiving email notifications for this group about new posts, events, and files in that group. Supported for Microsoft 365 groups only.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     | Group.ReadWrite.All                         |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | Not supported.                              |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /groups/{id}/unsubscribeByMail
```

## Request headers

| Header        | Value                                                                                                                                             |
| :------------ | :------------------------------------------------------------------------------------------------------------------------------------------------ |
| Authorization | Bearer {token}. Required.                                                                                                                         |
| Prefer        | return=minimal. If minimal response header is included in the request header, then a successful response returns `204 No Content` code. Optional. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns `200 OK` response code. It does not return anything in the response body.

## Example

#### Request

The following is an example of the request.

# [HTTP](#tab/http)

<!-- {
  "blockType": "request",
  "name": "group_unsubscribebymail"
}-->

```http
POST https://graph.microsoft.com/v1.0/groups/{id}/unsubscribeByMail
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/group-unsubscribebymail-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/group-unsubscribebymail-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/group-unsubscribebymail-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/group-unsubscribebymail-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/group-unsubscribebymail-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/group-unsubscribebymail-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
} -->

```http
HTTP/1.1 200 OK
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "group: unsubscribeByMail",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
