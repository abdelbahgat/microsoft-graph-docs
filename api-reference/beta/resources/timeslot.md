---
title: "timeSlot resource type"
description: "A time period."
ms.localizationpriority: medium
doc_type: resourcePageType
author: "vrod9429"
ms.prod: "outlook"
---

# timeSlot resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a time slot for a meeting.

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|end|[dateTimeTimeZone](datetimetimezone.md)|The date, time, and time zone that a period ends. |
|start|[dateTimeTimeZone](datetimetimezone.md)|The date, time, and time zone that a period begins.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.timeSlot"
}-->

```json
{
  "end": {"@odata.type": "microsoft.graph.dateTimeTimeZone"},
  "start": {"@odata.type": "microsoft.graph.dateTimeTimeZone"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "timeSlot resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


