---
author: spgraph-docs-team
ms.date: 09/10/2017
title: Get permission
ms.localizationpriority: medium
description: "Return the effective sharing permission for a particular permission resource."
ms.prod: "sharepoint"
doc_type: apiPageType
---
# Get sharing permission for a file or folder

Namespace: microsoft.graph

Return the effective sharing permission for a particular permission resource.

Effective permissions of an item can come from two sources: permissions set directly on the item itself or permissions that are inherited from the item's ancestors.

Callers can differentiate if the permission is inherited or not by checking the `inheritedFrom` property.
This property is an [ItemReference](../resources/itemreference.md) resource referencing the ancestor that the permission is inherited from.

[!INCLUDE [national-cloud-support](../../includes/all-clouds.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "permission_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/permission-get-permissions.md)]

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /drives/{drive-id}/items/{item-id}/permissions/{perm-id}
GET /groups/{group-id}/drive/items/{item-id}/permissions/{perm-id}
GET /me/drive/items/{item-id}/permissions/{perm-id}
GET /sites/{site-id}/drive/items/{item-id}/permissions/{perm-id}
GET /users/{user-id}/drive/items/{item-id}/permissions/{perm-id}
```

## Optional query parameters

This method support the [$select query parameter](/graph/query-parameters) to shape the response.

## Response

If successful, this method returns a `200 OK` response code and [Permission](../resources/permission.md) resource in the response body.

## Example

### Request

Here is an example of the request to access a permission on a folder.


# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "get-item-permission", "scopes": "files.read", "tags": "service.graph" } -->

```msgraph-interactive
GET /me/drive/items/{item-id}/permissions/{perm-id}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-item-permission-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-item-permission-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-item-permission-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-item-permission-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-item-permission-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-item-permission-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-item-permission-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-item-permission-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

If successful, this method returns a [Permission](../resources/permission.md) resource for the specified ID.

<!-- {"blockType": "response", "@odata.type": "microsoft.graph.permission", "truncated": true} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@deprecated.GrantedTo": "GrantedTo has been deprecated. Refer to GrantedToV2",
  "grantedTo": {
    "user": {
      "displayName": "Robin Danielsen",
      "id": "efee1b77-fb3b-4f65-99d6-274c11914d12"
    }
  },
  "grantedToV2": {
    "user": {
      "id": "efee1b77-fb3b-4f65-99d6-274c11914d12",
      "displayName": "Robin Danielsen"
    },
    "siteUser": {
      "id": "1",
      "displayName": "Robin Danielsen",
      "loginName": "Robin Danielsen"
    }
  },
  "id": "1",
  "roles": [ "write" ]
}
```

## Remarks

The [Permission](../resources/permission.md) resource uses _facets_ to provide information about the kind of permission represented by the resource.

Permissions with a [**link**](../resources/sharinglink.md) facet represent sharing links created on the item.
Sharing links contain a unique token that provides access to the item for anyone with the link.

Permissions with a [**invitation**](../resources/sharinginvitation.md) facet represent permissions added by inviting specific users or groups to have access to the file.

### Error responses

Read the [Error Responses][error-response] topic for more information about
how errors are returned.

[error-response]: /graph/errors

<!-- {
  "type": "#page.annotation",
  "description": "Get a DriveItem's sharing permissions",
  "keywords": "permission, permissions, sharing",
  "section": "documentation",
  "tocPath": "Sharing/Permissions",
  "suppressions": [
  ]
} -->
