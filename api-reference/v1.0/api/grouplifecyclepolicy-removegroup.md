---
title: "groupLifecyclePolicy: removeGroup"
description: "Removes a group from a lifecycle policy."
author: "psaffaie"
ms.localizationpriority: medium
ms.prod: "groups"
doc_type: apiPageType
---

# groupLifecyclePolicy: removeGroup

Namespace: microsoft.graph

Removes a group from a lifecycle policy.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
| :------------------------------------- | :------------------------------------------ |
| Delegated (work or school account)     | Directory.ReadWrite.All                     |
| Delegated (personal Microsoft account) | Not supported.                              |
| Application                            | Directory.ReadWrite.All                     |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /groupLifecyclePolicies/{id}/removeGroup
```

## Request headers

| Name          | Description               |
| :------------ | :------------------------ |
| Authorization | Bearer {token}. Required. |
| Content-Type  | application/json          |

## Request body

In the request body, provide a JSON object with the following parameters.

| Parameter | Type   | Description                                            |
| :-------- | :----- | :----------------------------------------------------- |
| groupId   | String | The identifier of the group to remove from the policy. |

## Response

If successful, this method returns `200 OK` response code. If the group is removed from the policy, a `true` value is returned in the response body. Otherwise, a `false` value is returned in the response body.

## Example

##### Request

<!-- {
  "blockType": "ignored",
  "name": "grouplifecyclepolicy_removegroup"
} -->

```http
POST https://graph.microsoft.com/v1.0/groupLifecyclePolicies/{id}/removeGroup
Content-type: application/json

{
  "groupId": "ffffffff-ffff-ffff-ffff-ffffffffffff"
}
```

##### Response

<!-- { "blockType": "response" } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": true
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "groupLifecyclePolicy: removegroup",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
