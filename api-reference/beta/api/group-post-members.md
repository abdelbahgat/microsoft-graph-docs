---
title: "Add members"
description: "Add a member to a Microsoft 365 or security group through the members navigation property."
ms.localizationpriority: medium
author: "psaffaie"
ms.prod: "groups"
doc_type: apiPageType
---

# Add members

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Add a member to a security or Microsoft 365 group through the **members** navigation property.

The following table shows the types of members that can be added to either security groups or Microsoft 365 groups.

| Object type             | Member of security group     | Member of Microsoft 365 group |
|-------------------------|-------------------------------|-------------------------------|
| User                   | ![Can be group member][Yes]   | ![Can be group member][Yes]   |
| Security group         | ![Can be group member][Yes]   | ![Cannot be group member][No] |
| Microsoft 365 group    | ![Cannot be group member][No] | ![Cannot be group member][No] |
| Device                 | ![Can be group member][Yes]   | ![Cannot be group member][No] |
| Service principal      | ![Can be group member][Yes]   | ![Cannot be group member][No] |
| Organizational contact | ![Can be group member][Yes]   | ![Cannot be group member][No] |


## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)                             |
| :------------------------------------- | :---------------------------------------------------------------------- |
| Delegated (work or school account)     | GroupMember.ReadWrite.All, Group.ReadWrite.All, Directory.ReadWrite.All |
| Delegated (personal Microsoft account) | Not supported.                                                          |
| Application                            | GroupMember.ReadWrite.All, Group.ReadWrite.All, Directory.ReadWrite.All |

> [!IMPORTANT]
> To add members to a role-assignable group, the calling user or app must also be assigned the _RoleManagement.ReadWrite.Directory_ permission.

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /groups/{group-id}/members/$ref
```

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}. Required. |

## Request body

In the request body, supply a JSON representation of a [directoryObject](../resources/directoryobject.md), [user](../resources/user.md) or [group](../resources/group.md) object to be added.

## Response

If successful, this method returns a `204 No Content` response code. It does not return anything in the response body. This method returns a `400 Bad Request` response code when the object is already a member of the group. This method returns a `404 Not Found` response code when the object being added doesn't exist.

## Example

### Request

The following is an example of the request.

# [HTTP](#tab/http)

<!-- {
  "blockType": "request",
  "name": "add_group_member"
}-->

```http
POST https://graph.microsoft.com/beta/groups/{group-id}/members/$ref
Content-type: application/json

{
  "@odata.id": "https://graph.microsoft.com/beta/directoryObjects/{id}"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/add-group-member-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/add-group-member-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/add-group-member-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/add-group-member-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/add-group-member-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/add-group-member-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

In the request body, supply a JSON representation of the `id` of the [directoryObject](../resources/directoryobject.md), [user](../resources/user.md), or [group](../resources/group.md) object you want to add.

### Response

The following is an example of the response.

<!-- {
  "blockType": "response"
} -->

```http
HTTP/1.1 204 No Content
```

## See also

- [Add member to team](team-post-members.md)
- [Update member's role in team](team-update-members.md)
- [Remove member from team](team-delete-members.md)



[Yes]: /graph/images/yesandnosymbols/greencheck.svg
[No]: /graph/images/yesandnosymbols/no.svg

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Create member",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
