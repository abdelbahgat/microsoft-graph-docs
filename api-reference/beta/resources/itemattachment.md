---
title: "itemAttachment resource type"
description: "A contact, event, or message that's attached to another event,"
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "outlook"
author: "abheek-das"
---

# itemAttachment resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [outlooktask-deprecate-sharedfeature](../../includes/outlooktask-deprecate-sharedfeature.md)]

A contact, event, or message that's attached to a user [event](../resources/event.md),
[message](../resources/message.md), [Outlook task](../resources/outlooktask.md), or [post](../resources/post.md).  

Derived from [attachment](attachment.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Get](../api/attachment-get.md) | [itemAttachment](itemattachment.md) |Read the properties, relationships, or raw contents of an itemAttachment object.|
|[Delete](../api/attachment-delete.md) | None |Delete itemAttachment object. |

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|contentType|String|The content type of the attachment.|
|id|String| The attachment ID.|
|isInline|Boolean|Set to true if the attachment is inline, such as an embedded image within the body of the item.|
|lastModifiedDateTime|DateTimeOffset|The last time and date that the attachment was modified.|
|name|String|The display name of the attachment.|
|size|Int32|The size in bytes of the attachment.|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|item|[OutlookItem](outlookitem.md)|The attached contact, message or event. Navigation property.|

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "baseType": "microsoft.graph.attachment",
  "keyProperty":"id",
  "optionalProperties": [
    "item"
  ],
  "@odata.type": "microsoft.graph.itemAttachment"
}-->

```json
{
  "contentType": "string",
  "id": "string (identifier)",
  "isInline": true,
  "lastModifiedDateTime": "String (timestamp)",
  "name": "string",
  "size": 1024
}

```
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "itemAttachment resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


