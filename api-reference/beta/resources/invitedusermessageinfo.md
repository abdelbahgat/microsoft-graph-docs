---
title: "invitedUserMessageInfo resource type"
description: "The invitedUserMessageInfo object allows you to configure the invitation message."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "identity-and-sign-in"
author: "Sammak"
---

# invitedUserMessageInfo resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The invitedUserMessageInfo object allows you to configure the [invitation](invitation.md) message.


## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|ccRecipients|[recipient](recipient.md) collection|Additional recipients the invitation message should be sent to. Currently only 1 additional recipient is supported.|
|customizedMessageBody|String|Customized message body you want to send if you don't want the default message.|
|messageLanguage|String|The language you want to send the default message in. If the customizedMessageBody is specified, this property is ignored, and the message is sent using the customizedMessageBody. The language format should be in ISO 639. The default is en-US.|

## JSON representation
Here is a JSON representation of the resource

<!-- {"blockType": "resource", "@odata.type": "microsoft.graph.invitedUserMessageInfo"} -->
```json
{
  "ccRecipients": [ {"@odata.type": "microsoft.graph.recipient"} ],
  "customizedMessageBody": "string",
  "messageLanguage": "string"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2016-22-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "invitedUserMessageInfo resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


