---
title: "ChartLegend resource type"
description: "Represents the legend in a chart."
author: "lumine2008"
ms.localizationpriority: medium
ms.prod: "excel"
doc_type: resourcePageType
---

# ChartLegend resource type

Namespace: microsoft.graph

Represents the legend in a chart.


## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get ChartLegend](../api/chartlegend-get.md) | [WorkbookChartLegend](chartlegend.md) |Read properties and relationships of chartLegend object.|
|[Update](../api/chartlegend-update.md) | [WorkbookChartLegend](chartlegend.md)	|Update ChartLegend object. |

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|overlay|boolean|Boolean value for whether the chart legend should overlap with the main body of the chart.|
|position|string|Represents the position of the legend on the chart. The possible values are: `Top`, `Bottom`, `Left`, `Right`, `Corner`, `Custom`.|
|visible|boolean|A boolean value the represents the visibility of a ChartLegend object.|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|format|[WorkbookChartLegendFormat](chartlegendformat.md)|Represents the formatting of a chart legend, which includes fill and font formatting. Read-only.|

## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "baseType": "microsoft.graph.entity",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.workbookChartLegend"
}-->

```json
{
  "format": {"@odata.type":"microsoft.graph.workbookChartLegendFormat"},
  "overlay": true,
  "position": "string",
  "visible": true
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "ChartLegend resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

