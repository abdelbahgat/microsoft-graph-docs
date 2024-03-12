---
title: "Get conversationMember"
description: "Get member of chat or channel."
author: "akjo"
ms.localizationpriority: high
ms.prod: "microsoft-teams"
doc_type: apiPageType
---

# Get conversationMember

Namespace: microsoft.graph

Retrieve a [conversationMember](../resources/conversationmember.md) from a [chat](../resources/chatmessage.md) or [channel](../resources/channel.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission Type|Permissions (from least to most privileged)|
|---------|-------------|
|Delegated (work or school account)| For **user** or **chat** resource: Chat.ReadBasic, Chat.Read, Chat.ReadWrite<br/><br/>For **channel** resource: ChannelMember.Read.All, ChannelMember.ReadWrite |
|Delegated (personal Microsoft account)|Not supported.|
|Application| For **user** or **chat** resource: Not supported.<br/><br/>For **channel** resource: TeamMember.Read.Group*, ChannelMember.Read.All, ChannelMember.ReadWrite.All |

> **Note**: Permissions marked with * use [resource-specific consent](/microsoftteams/platform/graph-api/rsc/resource-specific-consent).


## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /chats/{id}/members/{id}
GET /teams/{id}/channels/{id}/members/{id}
```

## Optional query parameters

This operation does not support the [OData query parameters](/graph/query-parameters) to customize the response.

## Request headers

| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [conversationMember](../resources/conversationmember.md) object in the response body.

## Example

### Request

Here is an example of the request.


<!-- {
  "blockType": "request",
  "name": "get_conversation_member_2"
}-->

```http
GET https://graph.microsoft.com/V1.0/chats/{id}/members/{id}
```


### Response

Here is an example of the response.

>**Note:** The response object shown here might be shortened for readability.
<!--
{
  "blockType": "response",
  "truncated": true,
  "name": "get_conversation_member_2",
  "@odata.type": "microsoft.graph.conversationMember"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "displayName": "display-name-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "conversation: member get",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
