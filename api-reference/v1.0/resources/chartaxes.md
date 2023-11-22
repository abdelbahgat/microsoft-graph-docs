---
title: "ChartAxes resource type"
description: "Represents the chart axes."
author: "lumine2008"
ms.localizationpriority: medium
ms.prod: "excel"
doc_type: resourcePageType
---

# ChartAxes resource type

Namespace: microsoft.graph

Represents the chart axes.


## Methods
None

## Properties
None

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|categoryAxis|[WorkbookChartAxis](chartaxis.md)|Represents the category axis in a chart. Read-only.|
|seriesAxis|[WorkbookChartAxis](chartaxis.md)|Represents the series axis of a 3-dimensional chart. Read-only.|
|valueAxis|[WorkbookChartAxis](chartaxis.md)|Represents the value axis in an axis. Read-only.|

## JSON representation

Here's a JSON representation of the resource.

<!--{
  "blockType": "resource",
  "optionalProperties": [],
  "baseType": "microsoft.graph.entity",
  "@odata.type": "microsoft.graph.workbookChartAxes"
}-->

```json
{
  "categoryAxis": {"@odata.type": "microsoft.graph.workbookChartAxis"},
  "seriesAxis": {"@odata.type": "microsoft.graph.workbookChartAxis"},
  "valueAxis": {"@odata.type": "microsoft.graph.workbookChartAxis"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "ChartAxes resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

