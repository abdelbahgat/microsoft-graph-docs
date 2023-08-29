---
title: "Change notifications for Microsoft Teams resources"
description: "Subscribe to changes to resources and resource data in Microsoft Teams by using the Microsoft Graph API. Learn about change notification types and payloads."
author: "anandab-msft"
ms.localizationpriority: high
ms.prod: "microsoft-teams"
ms.custom: scenarios:getting-started
---

# Change notifications for Microsoft Teams resources

Change notifications for Microsoft Teams resources using Microsoft Graph enable you to subscribe to changes (create, update, and delete) to a resource. Change notifications provide a low latency model by allowing you to maintain a [subscription](/graph/api/resources/webhooks). You can also get the resource data in the notifications and therefore avoid calling the API to get the payload.

> [!NOTE]
> The maximum time a subscription can last is 60 minutes; however, subscriptions can be renewed until the caller has permissions to access the resource.

## Change notification types

Microsoft Teams supports two types of change notifications:

- **Change notification to track all changes related to a resource across the tenant:** For example, you can subscribe to changes in messages in any channel across the tenant and get notified whenever a message is created, updated, or deleted in any channel in the tenant. These notifications may have [licensing and payment requirements](/graph/teams-licenses), such as change notifications for [messages](teams-changenotifications-chatmessage.md) and [membership](teams-changenotifications-chatMembership.md).

- **Change notification to track all changes for a specific resource:** For example, you can subscribe to changes in messages in a particular channel and get notified whenever a message is created, updated, or deleted in that channel.

For details about which resources support which types of change notifications, see [Microsoft Graph change notifications](webhooks.md).

## Supported resources
The following table lists the Microsoft Teams resources and corresponding resource paths that are currently supported.

| **Resource** | **Supported resource paths** | **Resource data can be included in notifications** |
|:----------------|:------------|:-----------------------------------------|
| Teams [channel](/graph/api/resources/channel) | Changes to channels in all teams:<br>`/teams/getAllChannels` <br>Changes to channel in a specific team:<br>`/teams/{id}/channels` | Yes |
| Teams [chat](/graph/api/resources/chat) | Changes to any chat in the tenant:<br>`/chats` <br>Changes to a specific chat:<br>`/chats/{id}` | Yes |
| Teams [chatMessage](/graph/api/resources/chatMessage) | Changes to chat messages in all channels in all teams:<br>`/teams/getAllMessages` <br>Changes to chat messages in a specific channel:<br>`/teams/{id}/channels/{id}/messages`<br>Changes to chat messages in all chats:<br>`/chats/getAllMessages` <br>Changes to chat messages in a specific chat:<br>`/chats/{id}/messages`<br>Changes to chat messages in all chats a particular user is part of:<br>`/users/{id}/chats/getAllMessages` | Yes |
| Teams [conversationMember](/graph/api/resources/conversationMember) | Changes to membership in a specific team:<br>`/teams/{id}/members` <br> Changes to membership in a specific chat:<br>`/chats/{id}/members` <br> Changes to membership in all chats:<br>`/chats/getAllMembers` <br> Changes to membership in all channels under a specific team:<br>`teams/{id}/channels/getAllMembers` | Yes |
| Teams [team](/graph/api/resources/team) | Changes to any team in the tenant:<br>`/teams` <br>Changes to a specific team:<br>`/teams/{id}` | Yes |
 

## Notification payloads

Depending on your subscription, you can either get the notification with resource data, or without resource data. Subscribing with resource data allows you to get the message payload along with the notification, which removes the need to call back and get the content.

### Notifications with resource data

For notifications with resource data, the payload looks like the following.  This payload is for a notification corresponding to the chat message resource. The actual notification includes the **resource** and **resourceData** properties, which represent the resource that has triggered the notification.

```json
{
    "value": [{
        "subscriptionId": "10493aa0-4d29-4df5-bc0c-ef742cc6cd7f",
        "changeType": "created",
        "clientState": "<<--SpecifiedClientState-->>",
        "subscriptionExpirationDateTime": "2021-02-02T10:30:34.9097561-08:00",
        "resource": "chats('19:8ea0e38b-efb3-4757-924a-5f94061cf8c2_97f62344-57dc-409c-88ad-c4af14158ff5@unq.gbl.spaces')/messages('1612289765949')",
        "resourceData": {
            "id": "1612289765949",
            "@odata.type": "#Microsoft.Graph.chatMessage",
            "@odata.id": "chats('19:8ea0e38b-efb3-4757-924a-5f94061cf8c2_97f62344-57dc-409c-88ad-c4af14158ff5@unq.gbl.spaces')/messages('1612289765949')"
        },
        "encryptedContent": {
            "data": "<<--EncryptedContent-->",
            "dataKey": "<<--EnryptedDataKeyUsedForEncryptingContent-->>",
            "encryptionCertificateId": "<<--IdOfTheCertificateUsedForEncryptingDataKey-->>",
            "encryptionCertificateThumbprint": "<<--ThumbprintOfTheCertificateUsedForEncryptingDataKey-->>"
        },
        "tenantId": "<<--TenantForWhichNotificationWasSent-->>"
    }],
    "validationTokens": ["<<--ValidationTokens-->>"]
}
```

For details about how to validate tokens and decrypt the payload, see [Set up change notifications that include resource data](webhooks-with-resource-data.md).

The decrypted notification payload looks like the following. The decrypted payload for the previous example conforms to the [chatMessage](/graph/api/resources/chatMessage) schema. The payload is similar to that returned by GET operations.

```json
{
  "id": "1612289992105",
  "replyToId": null,
  "etag": "1612289992105",
  "messageType": "message",
  "createdDateTime": "2021-02-02T18:19:52Z",
  "lastModifiedDateTime": "2021-02-02T18:19:52.105Z",
  "lastEditedDateTime": null,
  "deletedDateTime": null,
  "subject": null,
  "summary": null,
  "chatId": "19:8ea0e38b-efb3-4757-924a-5f94061cf8c2_97f62344-57dc-409c-88ad-c4af14158ff5@unq.gbl.spaces",
  "importance": "normal",
  "locale": "en-us",
  "webUrl": null,
  "from": {
    "application": null,
    "device": null,
    "user": {
      "id": "8ea0e38b-efb3-4757-924a-5f94061cf8c2",
      "displayName": "Ramjot Singh",
      "userIdentityType": "aadUser"
    },
    "conversation": null
  },
  "body": {
    "contentType": "text",
    "content": "test"
  },
  "channelIdentity": null,
  "attachments": [],
  "mentions": [],
  "policyViolation": null,
  "reactions": [],
  "replies": [],
  "hostedContents": []
}
```

### Notifications without resource data

Notifications without resource data give you enough information to make GET calls to get the resource. Subscriptions for notifications without resource data don't require an encryption certificate (because actual resource data is not sent over).

The payload looks like the following. This payload is for a message sent in a channel.

```json
{
  "subscriptionId": "9f9d1ed0-c9cc-42e7-8d80-a7fc4b0cda3c",
  "changeType": "created",
  "tenantId": "<<--TenantForWhichNotificationWasSent-->>",  
  "clientState": "<<--SpecifiedClientState-->>",
  "subscriptionExpirationDateTime": "2021-02-02T11:26:41.0537895-08:00",
  "resource": "teams('fbe2bf47-16c8-47cf-b4a5-4b9b187c508b')/channels('19:4a95f7d8db4c4e7fae857bcebe0623e6@thread.tacv2')/messages('1612293113399')",
  "resourceData": {
    "id": "1612293113399",
    "@odata.type": "#Microsoft.Graph.chatMessage",
    "@odata.id": "teams('fbe2bf47-16c8-47cf-b4a5-4b9b187c508b')/channels('19:4a95f7d8db4c4e7fae857bcebe0623e6@thread.tacv2')/messages('1612293113399')"
  }
}
```

Previous example above shows a notification that corresponds to a chat message resource. The actual notification includes the **resource** and **resourceData** properties, which represent the resource that has triggered the notification. The **resource** and **@odata.id** properties can be used to make calls to Microsoft Graph to get the payload of the resource.

> [!NOTE]
> GET calls always return the current state of the resource. If the resource is changed between when the notification is sent and when the resource is retrieved, the operation returns the updated resource.

## See also

- [Microsoft Graph change notifications](webhooks.md)
- [Microsoft Teams API overview](teams-concept-overview.md)
