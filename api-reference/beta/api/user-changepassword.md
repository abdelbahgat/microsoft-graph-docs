---
title: "user: changePassword"
description: "Update your own password."
ms.localizationpriority: medium
author: "jpettere"
ms.prod: "users"
doc_type: apiPageType
---

# user: changePassword

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Enable the user to update their password. Any user can update their password without belonging to any administrator role.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).


|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Directory.AccessAsUser.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /me/changePassword
```
## Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |
| Content-type  | application/json. Required.  |

## Request body
In the request body, provide a JSON object with the following parameters.

| Parameter	   | Type	|Description|
|:---------------|:--------|:----------|
| currentPassword | String | Your current password.|
| newPassword | String | Your new password.|

## Response

If successful, this method returns a `204 No Content` response code.

## Example
The following example shows a request to update your own password.

### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "user_changepassword"
}-->
```http
POST https://graph.microsoft.com/beta/me/changePassword
Content-type: application/json

{
    "currentPassword": "xWwvJ]6NMw+bWH-d",
    "newPassword": "0eM85N54wFxWwvJ]"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/user-changepassword-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/user-changepassword-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/user-changepassword-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/user-changepassword-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/user-changepassword-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/user-changepassword-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---



### Response
<!-- {
  "blockType": "response",
  "truncated": true
} -->
```http
HTTP/1.1 204 No Content
```

## See also
+ [Update the passwordProfile of a user to reset their password](../api/user-update.md#example-3-update-the-passwordprofile-of-a-user-to-reset-their-password)

<!-- uuid: a7c9a0de-8324-4f80-8d88-2e6d5838f3be
2021-06-24 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "user: changePassword",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->


