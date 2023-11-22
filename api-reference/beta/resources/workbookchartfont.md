---
title: "workbookChartFont resource type"
description: "This object represents the font attributes (font name, font size, color, etc.) for a chart object."
ms.localizationpriority: medium
author: "lumine2008"
ms.prod: "excel"
doc_type: resourcePageType
---

# workbookChartFont resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

This object represents the font attributes (font name, font size, color, etc.) for a chart object.


## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get workbookChartFont](../api/chartfont-get.md) | [workbookChartFont](workbookchartfont.md) |Read properties and relationships of chartFont object.|
|[Update](../api/chartfont-update.md) | [workbookChartFont](workbookchartfont.md)	|Update ChartFont object. |

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|bold|boolean|Represents the bold status of font.|
|color|string|HTML color code representation of the text color. for example #FF0000 represents Red.|
|italic|boolean|Represents the italic status of the font.|
|name|string|Font name (for example "Calibri")|
|size|double|Size of the font (for example 11)|
|underline|string|Type of underline applied to the font. The possible values are: `None`, `Single`.|

## Relationships
None


## JSON representation

Here's a JSON representation of the resource.

<!--{
  "blockType": "resource",
  "baseType": "microsoft.graph.entity",
  "optionalProperties": [],
  "@odata.type": "microsoft.graph.workbookChartFont"
}-->

```json
{
  "bold": true,
  "color": "string",
  "italic": true,
  "name": "string",
  "size": 1024,
  "underline": "string"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "ChartFont resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


