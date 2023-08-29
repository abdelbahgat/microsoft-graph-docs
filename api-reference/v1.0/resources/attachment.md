---
title: "attachment resource type"
description: "You can add related content to an event,"
ms.localizationpriority: high
author: "abheek-das"
ms.prod: "outlook"
doc_type: resourcePageType
---

# attachment resource type

Namespace: microsoft.graph

You can add related content to a user [event](../resources/event.md),
[message](../resources/message.md), or [post](../resources/post.md) in the form of an attachment.

**attachment** is the base resource for the following derived types of attachments:

* A file ([fileAttachment](../resources/fileattachment.md) resource)
* An item (contact, event or message, represented by an [itemAttachment](../resources/itemattachment.md) resource)
* A link to a file ([referenceAttachment](../resources/referenceattachment.md) resource)

Events in group calendars do not support attachments.

## Methods

The following methods apply to any of the derived types of attachments (**fileAttachment**,
**itemAttachment**, or **referenceAttachment**).

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[Get attachment](../api/attachment-get.md) | [attachment](attachment.md) |Read the properties, relationships, or raw contents of an attachment, attached to a user event, message, or post.|
|[Add attachment to a user event](../api/event-post-attachments.md) | [attachment](attachment.md) |Add a file, item, or link attachment to an event in a user calendar.|
|[Add attachment to a message](../api/message-post-attachments.md) | [attachment](attachment.md) |Add a file, item, or link attachment to a message.|
|[Add attachment to a post](../api/post-post-attachments.md) | [attachment](attachment.md) |Add a file, item, or link attachment to a post.|
|[List attachments of a user event](../api/event-list-attachments.md) | [attachment](attachment.md) collection | Get a list of attachments for an event in a user calendar. |
|[List attachments of a message](../api/message-list-attachments.md) | [attachment](attachment.md) collection | Get a list of attachments for a message. |
|[List attachments of a post](../api/post-list-attachments.md) | [attachment](attachment.md) collection | Get a list of attachments for a post. |
|[Delete](../api/attachment-delete.md) | None |Delete an attachment on an event, message, or post. |

## Properties

The following are the base properties of any attachment resource. Refer to the specific type of attachment ([fileAttachment](../resources/fileattachment.md),
[itemAttachment](../resources/itemattachment.md), or [referenceAttachment](../resources/referenceattachment.md)) for additional properties.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|contentType|String|The MIME type.|
|id|String| Read-only.|
|isInline|Boolean|`true` if the attachment is an inline attachment; otherwise, `false`.|
|lastModifiedDateTime|DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|name|String|The attachment's file name.|
|size|Int32|The length of the attachment in bytes.|

## Relationships
None

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "baseType": "microsoft.graph.entity",
  "abstract": true,
  "optionalProperties": [

  ],
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.attachment"
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
<!-- {
  "type": "#page.annotation",
  "description": "attachment resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

