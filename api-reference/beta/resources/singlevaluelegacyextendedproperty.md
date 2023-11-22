---
title: "singleValueLegacyExtendedProperty resource type"
description: "An extended property that contains a single value. "
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: cloud-pc
author: "SuryaLashmiS"
---

# singleValueLegacyExtendedProperty resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

[!INCLUDE [outlooktask-deprecate-sharedfeature](../../includes/outlooktask-deprecate-sharedfeature.md)]

An extended property that contains a single value.

See [Extended properties overview](../resources/extended-properties-overview.md) for more information about when to use
open extensions or extended properties, and how to specify extended properties.


## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Post](../api/singlevaluelegacyextendedproperty-post-singlevalueextendedproperties.md) | A supported resource instance: [message](../resources/message.md), [mailFolder](../resources/mailfolder.md), [event](../resources/event.md), [calendar](../resources/calendar.md), [contact](../resources/contact.md), [contactFolder](../resources/contactfolder.md), [Outlook task](../resources/outlooktask.md), or [Outlook task folder](../resources/outlooktaskfolder.md), but not group [post](../resources/post.md). | Create a **singleValueLegacyExtendedProperty** in a new or existing instance of a supported resource. |
|[Get](../api/singlevaluelegacyextendedproperty-get.md) |One or a collection of supported resource instance ([message](../resources/message.md), [mailFolder](../resources/mailfolder.md), [event](../resources/event.md), [calendar](../resources/calendar.md), [contact](../resources/contact.md), [contactFolder](../resources/contactfolder.md), [Outlook task](../resources/outlooktask.md), [Outlook task folder](../resources/outlooktaskfolder.md), or group [post](../resources/post.md)), or one such instance expanded with a [singleValueLegacyExtendedProperty](singlevaluelegacyextendedproperty.md) object. |Get a resource instance with an extended property using `$expand` or `$filter`.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|string|The property identifier. Read-only.|
|value|string|A property value.|

## Relationships
None


## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.singleValueLegacyExtendedProperty"
}-->

```json
{
  "id": "string (identifier)",
  "value": "string"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "singleValueLegacyExtendedProperty resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


