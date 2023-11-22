---
title: "Permanently delete item (directory object)"
description: "Permanently delete a recently deleted application, group, service principal, or user from deleted items."
author: "keylimesoda"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# Permanently delete item (directory object)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Permanently delete a recently deleted [application](../resources/application.md), [group](../resources/group.md), [servicePrincipal](../resources/serviceprincipal.md), or [user](../resources/user.md) object from [deleted items](../resources/directory.md). After an item is permanently deleted, it **cannot** be restored.

Administrative units **cannot** be permanently deleted by using the **deletedItems** API. Soft-deleted administrative units will be permanently deleted 30 days after initial deletion unless they are restored.

[!INCLUDE [national-cloud-support](../../includes/all-clouds.md)]

## Permissions

The following table shows the least privileged permission or permissions required to call this API on each supported resource type. Follow [best practices](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions) to request least privileged permissions. For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

| Supported resource | Delegated (work or school account) | Delegated (personal Microsoft account) | Application |
|:-|:-|:-|:-|
| [application](../resources/application.md) | Application.ReadWrite.All | Not supported. | Application.ReadWrite.OwnedBy |
| [group](../resources/group.md) | Group.ReadWrite.All | Not supported. | Not supported. |
| [servicePrincipal](../resources/serviceprincipal.md) | Application.ReadWrite.All | Not supported. | Application.ReadWrite.OwnedBy |
| [user](../resources/user.md) | User.ReadWrite.All | Not supported. | Not supported. |

[!INCLUDE [rbac-deleted-items-delete-apis](../includes/rbac-for-apis/rbac-deleted-items-delete-apis.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
DELETE /directory/deleteditems/{id}
```

## Request headers
| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer &lt;code&gt; *Required*|
| Accept  | application/json |

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns `204 No Content` response code. It doesn't return anything in the response body.

## Example
### Request


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "delete_directory_deleteditem"
}-->
```http
DELETE https://graph.microsoft.com/beta/directory/deleteditems/46cc6179-19d0-473e-97ad-6ff84347bbbb
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/delete-directory-deleteditem-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/delete-directory-deleteditem-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
Note: The response object shown here might be shortened for readability.
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
  "description": "Delete directory",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->


