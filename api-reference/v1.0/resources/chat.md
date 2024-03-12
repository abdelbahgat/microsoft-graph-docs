---
title: "chat resource type"
description: "A chat is a collection of chatMessages between one or more participants."
author: "RamjotSingh"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# chat resource type

Namespace: microsoft.graph

A chat is a collection of [chatMessages](chatmessage.md) between one or more participants. Participants can be users or apps.

> **Note**: If the chat is associated with an [onlineMeeting](../resources/onlinemeeting.md) instance, then some of the listed methods will transitively impact the meeting.

## Methods

|  Method       |  Return Type  | Description| 
|:---------------|:--------|:----------|
| **Chat management** |||
|[Create chat](../api/chat-post.md) | [chat](chat.md) | Create a new chat.| 
|[Get chat](../api/chat-get.md) | [chat](chat.md) | Read properties and relationships of the chat.| 
|[Update chat](../api/chat-patch.md) | [chat](chat.md) | Update properties of the chat.|
|[List chat members](../api/chat-list-members.md) | [conversationMember](conversationmember.md) collection | Get the list of all users in the chat.| 
|[Add chat member](../api/chat-post-members.md) | Location header | Add a user to the chat.| 
|[Get chat member](../api/chat-get-members.md) | [conversationMember](conversationmember.md) | Get a single user in the chat.| 
|[Remove chat member](../api/chat-delete-members.md)|None|Remove a user from the chat.|
|[Get chat between user and app](../api/userscopeteamsappinstallation-get-chat.md) | [chat](chat.md)| Get one-on-one chat between user and the app |
| **Messages** |||
|[List messages in chat](../api/chat-list-messages.md)  | [chatMessage](../resources/chatmessage.md) | Get messages in a chat. | 
|[Get message in chat](../api/chatmessage-get.md)  | [chatMessage](../resources/chatmessage.md) | Get a single message in a chat. | 
|[Get messages across all chats for user](../api/chats-getallmessages.md)| [chat](chat.md) collection| Get messages from all chats that a user is a participant in. |
| **Apps** |||
|[List apps in chat](../api/chat-list-installedapps.md) |[teamsAppInstallation](teamsappinstallation.md) collection | List apps installed in a chat (and associated meeting).|
|[Get app in chat](../api/chat-get-installedapps.md) | [teamsAppInstallation](teamsappinstallation.md) | Get a specific app installed in a chat (and associated meeting).|
|[Add app in chat](../api/chat-post-installedapps.md) | | Add (install) an app in a chat (and associated meeting).|
|[Upgrade app in chat](../api/chat-teamsappinstallation-upgrade.md) | None | Update to the latest version of the app installed in chat (and associated meeting).|
|[Uninstall app from chat](../api/chat-delete-installedapps.md) | None | Remove (uninstall) app from a chat (and associated meeting).|
| **Tabs** |||
|[List tabs in chat](../api/chat-list-tabs.md) | [teamsTab](teamstab.md) | List tabs pinned to a chat (and associated meeting).|
|[Get tab in chat](../api/chat-get-tabs.md) | [teamsTab](teamstab.md) | Get a specific tab pinned to a chat (and associated meeting).|
|[Add tab to chat](../api/chat-post-tabs.md) | [teamsTab](teamstab.md) | Add (pin) a tab to a chat (and associated meeting).|
|[Update tab in chat](../api/chat-patch-tabs.md) | [teamsTab](teamstab.md) | Update the properties of a tab in a chat (and associated meeting).|
|[Remove tab from chat](../api/chat-delete-tabs.md) | None | Remove (unpin) a tab from a chat (and associated meeting).|
| **Pinned messages** |||
|[List pinned messages](../api/chat-list-pinnedmessages.md)|[pinnedChatMessageInfo](../resources/pinnedchatmessageinfo.md) collection|Get a list of pinned messages in a chat.|
|[Pin a message](../api/chat-post-pinnedmessages.md)|[pinnedChatMessageInfo](../resources/pinnedchatmessageinfo.md)|Pin a chat message in a chat.|
|[Unpin a message](../api/chat-delete-pinnedmessages.md)|None|Unpin a message from a chat.|

>**Note:** When using application permissions, be sure you know how to get the chat ID. Because listing chats with application permissions is not supported, not all scenarios are possible. It is possible to get chat IDs with delegated permissions, and from [change notifications for /chats/getAllMessages](../api/subscription-post-subscriptions.md) with application permissions.

## Properties

| Property   | Type |Description|
|:---------------|:--------|:----------|
| chatType| [chatType](../resources/chat.md#chattype-values) | Specifies the type of chat. Possible values are: `group`, `oneOnOne`, `meeting`, `unknownFutureValue`.|
| createdDateTime| dateTimeOffset|  Date and time at which the chat was created. Read-only.|
| id| String| The chat's unique identifier. Read-only.|
| lastUpdatedDateTime| dateTimeOffset|  Date and time at which the chat was renamed or list of members were last changed. Read-only.|
| onlineMeetingInfo | [teamworkOnlineMeetingInfo](../resources/teamworkonlinemeetinginfo.md) | Represents details about an online meeting. If the chat isn't associated with an online meeting, the property is empty. Read-only.|
| tenantId| String | The identifier of the tenant in which the chat was created. Read-only.|
| topic| String|  (Optional) Subject or topic for the chat. Only available for group chats.|
| viewpoint|[chatViewpoint](../resources/chatviewpoint.md)|Represents caller-specific information about the chat, such as last message read date and time. This property is populated only when the request is made in a delegated context.|
| webUrl | String| The URL for the chat in Microsoft Teams. The URL should be treated as an opaque blob, and not parsed. Read-only. |

### chatType values 

| Member             | Value | Description               |
| :----------------- | :---- | :------------------------ |
|oneOnOne            | 0     | Indicates that the chat is a 1:1 chat. The roster size is fixed for this type of chat; members cannot be removed/added.|
|group               | 1     | Indicates that the chat is a group chat. The roster size (of at least two people) can be updated for this type of chat. Members can be removed/added later.|
|meeting             | 2     | Indicates that the chat is associated with an online meeting. This type of chat is only created as part of the creation of an online meeting.|
|unknownFutureValue  | 3     | Evolvable enumeration sentinel value. Do not use. |

## Relationships

| Relationship | Type |Description|
|:---------------|:--------|:----------|
| installedApps | [teamsAppInstallation](teamsappinstallation.md) collection | A collection of all the apps in the chat. Nullable. |
| lastMessagePreview | [chatMessageInfo](chatmessageinfo.md)| Preview of the last message sent in the chat. Null if no messages have been sent in the chat. Currently, only the [list chats](../api/chat-list.md) operation supports this property.|
| members | [conversationMember](conversationmember.md) collection | A collection of all the members in the chat. Nullable. |
| messages | [chatMessage](chatmessage.md) collection | A collection of all the messages in the chat. Nullable. |
| pinnedMessages | [pinnedChatMessageInfo](pinnedchatmessageinfo.md) collection | A collection of all the pinned messages in the chat. Nullable. |
| tabs | [teamsTab](teamstab.md) collection | A collection of all the tabs in the chat. Nullable. |

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.chat"
}-->

```json
{
  "createdDateTime": "dateTimeOffset",
  "chatType": "string",
  "id": "string (identifier)",
  "lastUpdatedDateTime": "dateTimeOffset",
  "onlineMeetingInfo": {
    "@odata.type": "microsoft.graph.teamworkOnlineMeetingInfo"
  },
  "tenantId": "string",
  "topic": "string",
  
  "viewpoint": {
    "@odata.type": "microsoft.graph.chatViewpoint"
  },
  "webUrl": "string",
}
```

## See also

- [channel](channel.md)
- [chatMessage](chatmessage.md)
- [Chat lifecycle C# sample](https://github.com/OfficeDev/Microsoft-Teams-Samples/blob/main/samples/graph-chat-lifecycle/csharp)
- [Chat lifecycle Node.js sample](https://github.com/OfficeDev/Microsoft-Teams-Samples/blob/main/samples/graph-chat-lifecycle/nodejs)


<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "chat resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}
-->


