---
title: "Update authentication signInPreferences"
description: "Update the properties of a user's authentication sign in preferences."
author: "jpettere"
ms.reviewer: intelligentaccesspm
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: apiPageType
---

# Update authentication signInPreferences
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [signInPreferences](../resources/signInPreferences.md) object.

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "authentication_update" } -->
[!INCLUDE [permissions-table](../includes/permissions/authentication-update-permissions.md)]

[!INCLUDE [rbac-authentication-methods-apis-write-others](../includes/rbac-for-apis/rbac-authentication-methods-apis-write-others.md)]


## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /users/{id | userPrincipalName}/authentication/signInPreferences
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


|Property|Type|Description|
|:---|:---|:---|
|isSystemPreferredAuthenticationMethodEnabled|Boolean|Indicates whether the credential preferences of the system are enabled.|
|userPreferredMethodForSecondaryAuthentication|userDefaultAuthenticationMethodType|The default second-factor method used by the user when signing in. If a user is enabled for system-preferred authentication, then this value is ignored except for a few scenarios where a user is authenticating via NPS extension or ADFS adapter. Possible values are `push`, `oath`, `voiceMobile`, `voiceAlternateMobile`, `voiceOffice`, `sms`, and `unknownFutureValue`|



## Response

If successful, this method returns a `204 No Content` response code. It doesn't return anything in the response body.

## Examples

### Request
The following is an example of a request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "update_authentication"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/users/071cc716-8147-4397-a5ba-b2105951cc0b/authentication/signInPreferences
Content-Type: application/json

{
  "userPreferredMethodForSecondaryAuthentication": "oath"
}
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/update-authentication-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/update-authentication-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
```http
HTTP/1.1 204 No Content
```


