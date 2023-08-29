---
title: "workbookChartGridlines resource type"
description: "Represents major or minor gridlines on a chart axis."
author: "lumine2008"
ms.localizationpriority: medium
ms.prod: "excel"
doc_type: resourcePageType
---

# workbookChartGridlines resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents major or minor gridlines on a chart axis.


## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get workbookChartGridlines](../api/chartgridlines-get.md) | [workbookChartGridlines](workbookchartgridlines.md) |Read properties and relationships of chartGridlines object.|
|[Update](../api/chartgridlines-update.md) | [workbookChartGridlines](workbookchartgridlines.md)	|Update ChartGridlines object. |

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|visible|boolean|Boolean value representing if the axis gridlines are visible or not.|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|format|[workbookChartGridlinesFormat](workbookchartgridlinesformat.md)|Represents the formatting of chart gridlines. Read-only.|

## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "baseType": "microsoft.graph.entity",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.workbookChartGridlines"
}-->

```json
{
  "visible": true
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "ChartGridlines resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


