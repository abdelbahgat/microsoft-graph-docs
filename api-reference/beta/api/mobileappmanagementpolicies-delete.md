---
title: "Delete mobileAppManagementPolicy"
description: "Delete a mobile app management policy."
author: "michaelrm97"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# Delete mobileAppManagementPolicy

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Delete a [mobilityManagementPolicy](../resources/mobilitymanagementpolicy.md) object.

> [!NOTE]
> This operation is only supported when the policy is no longer valid; that is, when the **isValid** property is false, which indicates that the service principal associated with the application for this policy has been deleted.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Policy.ReadWrite.MobilityManagement|
|Delegated (personal Microsoft account) | Not supported.|
|Application | Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
DELETE /policies/mobileAppManagementPolicies/{id}
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body.

## Examples

### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "delete_mobilitymanagementpolicy_forid_app"
}
-->

``` http
DELETE https://graph.microsoft.com/beta/policies/mobileAppManagementPolicies/ab90bacf-55a3-4a3e-839a-aa4b74e4f020
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/delete-mobilitymanagementpolicy-forid-app-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/delete-mobilitymanagementpolicy-forid-app-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/delete-mobilitymanagementpolicy-forid-app-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/delete-mobilitymanagementpolicy-forid-app-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/delete-mobilitymanagementpolicy-forid-app-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/delete-mobilitymanagementpolicy-forid-app-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

<!-- {
  "blockType": "response",
  "truncated": true
}
-->

``` http
HTTP/1.1 204 No Content
```
