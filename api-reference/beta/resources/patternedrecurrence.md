---
title: "patternedRecurrence resource type"
description: "The recurrence pattern and range."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "governance"
author: "iamgirishck"
---

# patternedRecurrence resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The recurrence pattern and range. This shared object is used to define the recurrence of [access reviews](accessreviewscheduledefinition.md), [calendar events](event.md), and [access package assignments](accesspackageassignment.md) in Azure AD.

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|pattern|[recurrencePattern](recurrencepattern.md)|The frequency of an event. Do not specify for a one-time access review. <br/><br/> For access reviews: <li>Do not specify this property for a one-time access review. <li>  Only **interval**, **dayOfMonth**, and **type** (`weekly`, `absoluteMonthly`) properties of [recurrencePattern](recurrencepattern.md) are supported.|
|range|[recurrenceRange](recurrencerange.md)|The duration of an event.|

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.patternedRecurrence"
}-->

```json
{
  "pattern": {"@odata.type": "microsoft.graph.recurrencePattern"},
  "range": {"@odata.type": "microsoft.graph.recurrenceRange"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "patternedRecurrence resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


