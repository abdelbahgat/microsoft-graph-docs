---
title: "List group members"
description: "Get a list of the group's direct members. A group can have users, organizational contacts, devices, service principals and other groups as members."
ms.localizationpriority: high
author: "psaffaie"
ms.prod: "groups"
doc_type: apiPageType
---

# List group members

Namespace: microsoft.graph

Get a list of the group's direct members. A group can have users, organizational contacts, devices, service principals and other groups as members. Currently service principals are not listed as group members due to staged roll-out of service principals on Graph V1.0 endpoint. This operation is not transitive.

When a group contains more than 100 members, Microsoft Graph returns a `@odata.nextLink` property in the response that contains a URL to the next page of results. If that property is present, continue making additional requests with the `@odata.nextLink` URL in each response, until all the results are returned, as described in [paging Microsoft Graph data in your app](/graph/paging).

An attempt to filter by an OData cast that represents an unsupported member type returns a `400 Bad Request` error with the `Request_UnsupportedQuery` code.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)                                                              |
| :------------------------------------- | :------------------------------------------------------------------------------------------------------- |
| Delegated (work or school account)     | GroupMember.Read.All, Group.Read.All, GroupMember.ReadWrite.All, Group.ReadWrite.All, Directory.Read.All |
| Delegated (personal Microsoft account) | Not supported.                                                                                           |
| Application                            | GroupMember.Read.All, Group.Read.All, GroupMember.ReadWrite.All, Group.ReadWrite.All, Directory.Read.All |

[!INCLUDE [limited-info](../../includes/limited-info.md)]

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /groups/{id}/members
```

## Optional query parameters

This method supports the `$filter`, `$count`, `$select`, `$search`, and `$expand` [OData query parameters](/graph/query-parameters) to help customize the response. OData cast is also enabled, for example, you can cast to get just the group members that are users. You can use `$search` on the **displayName** and **description** properties. When items are added or updated for this resource, they are specially indexed for use with the `$count` and `$search` query parameters. There can be a slight delay between when an item is added or updated and when it is available in the index.

## Request headers

| Header           | Value                                                                                                                                                                                                             |
| :--------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Authorization    | Bearer {token}. Required.                                                                                                                                                                                         |
| ConsistencyLevel | eventual. This header and `$count` are required when using the `$search`, `$filter`, `$orderby`, or OData cast query parameters. It uses an index that might not be up-to-date with recent changes to the object. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [directoryObject](../resources/directoryobject.md) objects in the response body.

An attempt to filter by an OData cast that represents an unsupported member type returns a `400 Bad Request` error with the `Request_UnsupportedQuery` code. For example, `/groups/{id}}/members/microsoft.graph.group` when the group is a Microsoft 365 group will return this error, because Microsoft 365 groups cannot have other groups as members.

## Examples

### Example 1: Get the direct membership in a group

#### Request

The following is an example of the request.

# [HTTP](#tab/http)

<!-- {
  "blockType": "request",
  "name": "get_group_members"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/groups/02bd9fd6-8f93-4758-87c3-1fb73740a315/members
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-group-members-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-group-members-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-group-members-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-group-members-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-group-members-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-group-members-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.directoryObject",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#directoryObjects",
  "value": [
    {
      "id": "11111111-2222-3333-4444-555555555555",
      "mail": "user1@contoso.com"
    }
  ]
}
```

### Example 2: Get only a count of all membership

#### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "get_count_only"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/groups/02bd9fd6-8f93-4758-87c3-1fb73740a315/members/$count
ConsistencyLevel: eventual
```

#### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "name": "get_count_only",
  "truncated": true,
  "@odata.type": "string"
} -->

```http
HTTP/1.1 200 OK
Content-type: text/plain

893
```

### Example 3: Use OData cast to get only a count of user membership

#### Request

The following is an example of the request.

<!-- {
  "blockType": "request",
  "name": "get_count_user_only"
}-->

```http
GET https://graph.microsoft.com/v1.0/groups/{id}/members/microsoft.graph.user/$count
ConsistencyLevel: eventual
```

#### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "name": "get_count_user_only",
  "truncated": true,
  "@odata.type": "string"
} -->

```http
HTTP/1.1 200 OK
Content-type: text/plain

893
```

### Example 4: Use $searchand OData cast to get user membership in groups with display names that contain the letters 'Pr' including a count of returned objects

#### Request

The following is an example of the request.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_pr_count"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/groups/{id}/members/microsoft.graph.user?$count=true&$orderby=displayName&$search="displayName:Pr"&$select=displayName,id
ConsistencyLevel: eventual
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-pr-count-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-pr-count-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-pr-count-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-pr-count-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-pr-count-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [snippet-not-available](../includes/snippets/snippet-not-available.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.user",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context":"https://graph.microsoft.com/v1.0/$metadata#users(displayName,id)",
  "@odata.count":7,
  "value":[
    {
      "displayName":"Joseph Price",
      "id":"11111111-2222-3333-4444-555555555555"
    },
    {
      "displayName":"Preston Morales",
      "id":"66666666-7777-8888-9999-000000000000"
    }
  ]
}
```

### Example 5: Use $filter to get group membership with a display name that starts with the letter 'A' including a count of returned objects

#### Request

The following is an example of the request.

# [HTTP](#tab/http)

<!-- {
  "blockType": "request",
  "name": "list_groups_members_startswith"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/groups/{id}/members?$count=true&$filter=startswith(displayName, 'a')
ConsistencyLevel: eventual
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/list-groups-members-startswith-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/list-groups-members-startswith-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/list-groups-members-startswith-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/list-groups-members-startswith-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/list-groups-members-startswith-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/list-groups-members-startswith-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.directoryObject",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context":"https://graph.microsoft.com/v1.0/$metadata#directoryObjects",
  "@odata.count":76,
  "value":[
    {
      "displayName":"AAD Contoso Users",
      "mail":"AADContoso_Users@contoso.com"
    }
  ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List members",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->
