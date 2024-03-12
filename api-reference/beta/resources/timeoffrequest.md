---
title: "timeOffRequest resource type"
description: "Represents a type of shift request to take timeoff."
ms.localizationpriority: medium
author: "akumar39"
ms.prod: "microsoft-teams"
doc_type: "resourcePageType"
---

# timeOffRequest resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a type of shift request to take [timeOff](../resources/timeoff.md).

## Methods

| Method       | Return type | Description |
|:-------------|:------------|:------------|
| [List](../api/timeoffrequest-list.md) | [timeOffRequest](timeoffrequest.md) collection | Get the list of **timeOffRequest** objects in this schedule.|
| [Get](../api/timeoffrequest-get.md) | [timeOffRequest](timeoffrequest.md) | Read the properties and relationships of a **timeOffRequest** object. |
| [Delete](../api/timeoffrequest-delete.md) | None | Delete a **timeOffRequest** object. |
| [Approve](../api/timeoffrequest-approve.md)|None|Approve a time off request.|
| [Decline](../api/timeoffrequest-decline.md)|None|Decline a time off request.|

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|endDateTime|DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|startDateTime|DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|timeOffReasonId|String|The reason for the time off.|

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.timeOffRequest"
}-->

```json
{
  "endDateTime": "String (timestamp)",
  "startDateTime": "String (timestamp)",
  "timeOffReasonId": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "timeOffRequest resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


