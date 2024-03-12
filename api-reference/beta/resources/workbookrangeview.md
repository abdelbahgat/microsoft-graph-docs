---
title: "workbookRangeView resource type"
description: "RangeView represents a set of visible cells of the parent range."
author: "lumine2008"
ms.localizationpriority: medium
ms.prod: "excel"
doc_type: resourcePageType
---

# workbookRangeView resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

RangeView represents a set of visible cells of the parent range.

## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[List rows](../api/workbookrangeview-list-rows.md) |[workbookRangeView](workbookrangeview.md) collection| Get a workbookRangeView object collection.|
|[Itemat](../api/workbookrangeview-itemat.md)|[workbookRangeView](workbookrangeview.md)|Get a range view item based in index.|
|[Range](../api/workbookrangeview-range.md)|[workbookRange](workbookrange.md)|Return the range object associated with the range view|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|columnCount|Int32|Returns the number of visible columns. Read-only.|
|formulas|Json|Represents the formula in A1-style notation.	|
|formulasLocal|Json|Represents the formula in A1-style notation, in the user's language and number-formatting locale. For example, the English "=SUM(A1, 1.5)" formula would become "=SUMME(A1; 1,5)" in German.	|
|formulasR1C1|Json|Represents the formula in R1C1-style notation.	|
|index|Int32|Index of the range.|
|numberFormat|Json|Represents Excel's number format code for the given cell. Read-only.	|
|rowCount|Int32|Returns the number of visible rows. Read-only.	|
|text|Json|Text values of the specified range. The Text value will not depend on the cell width. The # sign substitution that happens in Excel UI will not affect the text value returned by the API. Read-only.	|
|valueTypes|Json|Represents the type of data of each cell. Read-only. Possible values are: Unknown, Empty, String, Integer, Double, Boolean, Error.	|
|values|Json|Represents the raw values of the specified range view. The data returned could be of type string, number, or a boolean. Cell that contain an error will return the error string.	|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|rows|[workbookRangeView](workbookrangeview.md) collection| Represents a collection of range views associated with the range. Read-only.	Read-only.|

## JSON representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "optionalProperties": [  ],
  "keyProperty": "id",
  "baseType":"microsoft.graph.entity",
  "@odata.type": "microsoft.graph.workbookRangeView"
}-->
```json
{
  "cellAddresses": "Json",
  "columnCount": 1024,
  "formulas": "Json",
  "formulasLocal": "Json",
  "formulasR1C1": "Json",
  "id": "String (identifier)",
  "index": 1024,
  "numberFormat": "Json",
  "rowCount": 1024,
  "text": "Json",
  "valueTypes": "Json",
  "values": "Json"
}
```


