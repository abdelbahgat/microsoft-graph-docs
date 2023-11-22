---
title: "educationPointsOutcome resource type"
description: "An educationOutcome that gives a numerical grade."
ms.localizationpriority: medium
author: "sharad-sharma-msft"
ms.prod: "education"
doc_type: "resourcePageType"
---

# educationPointsOutcome resource type

Namespace: microsoft.graph

An [educationOutcome](educationoutcome.md) that gives a numerical grade.

## Methods

| Method       | Return Type | Description |
|:-------------|:------------|:------------|
| [Update educationOutcome](../api/educationoutcome-update.md) | [educationOutcome](educationoutcome.md) | Update educationOutcome object. |

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|id|String|Unique identifier for the educationPointsOutcome.|
|points|[educationAssignmentPointsGrade](educationassignmentpointsgrade.md)|The numeric grade the teacher has given the student for this assignment.|
|publishedPoints|[educationAssignmentPointsGrade](educationassignmentpointsgrade.md)|A copy of the points property that is made when the grade is released to the student.|

## Relationships

None

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationPointsOutcome",
  "keyProperty": "id"
}-->

```json
{
  "id": "String (identifier)",
  "points": {"@odata.type": "microsoft.graph.educationAssignmentPointsGrade"},
  "publishedPoints": {"@odata.type": "microsoft.graph.educationAssignmentPointsGrade"}
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "educationPointsOutcome resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

