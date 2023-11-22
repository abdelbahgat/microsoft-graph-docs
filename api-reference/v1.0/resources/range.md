---
title: "Range resource type"
description: "Range represents a set of one or more contiguous cells such as a cell, a row, a column, block of cells, etc."
ms.localizationpriority: high
author: "lumine2008"
ms.prod: "excel"
doc_type: resourcePageType
---

# Range resource type

Namespace: microsoft.graph

Range represents a set of one or more contiguous cells such as a cell, a row, a column, block of cells, etc.


## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[Get Range](../api/range-get.md) | [Range](range.md) |Read properties and relationships of range object.|
|[Update](../api/range-update.md) | [Range](range.md)	|Update Range object. |
|[Boundingrect](../api/range-boundingrect.md)|[Range](range.md)|Gets the smallest range object that encompasses the given ranges. For example, the GetBoundingRect of "B2:C5" and "D10:E15" is "B2:E16".|
|[Cell](../api/range-cell.md)|[Range](range.md)|Gets the range object containing the single cell based on row and column numbers. The cell can be outside the bounds of its parent range, so long as it's stays within the worksheet grid. The returned cell is located relative to the top left cell of the range.|
|[Column](../api/range-column.md)|[Range](range.md)|Gets a column contained in the range.|
|[Columnsafter](../api/workbookrange-columnsafter.md)|[workbookRangeView](workbookrangeview.md)|Gets some columns to the right of the given range.|
|[Columnsbefore](../api/workbookrange-columnsbefore.md)|[workbookRangeView](workbookrangeview.md)|Gets some columns to the left of the given range.|
|[Entirecolumn](../api/range-entirecolumn.md)|[Range](range.md)|Gets an object that represents the entire column of the range.|
|[Entirerow](../api/range-entirerow.md)|[Range](range.md)|Gets an object that represents the entire row of the range.|
|[Intersection](../api/range-intersection.md)|[Range](range.md)|Gets the range object that represents the rectangular intersection of the given ranges.|
|[Lastcell](../api/range-lastcell.md)|[Range](range.md)|Gets the last cell within the range. For example, the last cell of "B2:D5" is "D5".|
|[Lastcolumn](../api/range-lastcolumn.md)|[Range](range.md)|Gets the last column within the range. For example, the last column of "B2:D5" is "D2:D5".|
|[Lastrow](../api/range-lastrow.md)|[Range](range.md)|Gets the last row within the range. For example, the last row of "B2:D5" is "B5:D5".|
|[Offsetrange](../api/range-offsetrange.md)|[Range](range.md)|Gets an object that represents a range that's offset from the specified range. The dimension of the returned range matches this range. If the resulting range is forced outside the bounds of the worksheet grid, an exception is thrown.|
|[Row](../api/range-row.md)|[Range](range.md)|Gets a row contained in the range.|
|[Rowsabove](../api/workbookrange-rowsabove.md)|[workbookRangeView](workbookrangeview.md)|Gets some rows above a given range.|
|[Rowsbelow](../api/workbookrange-rowsbelow.md)|[workbookRangeView](workbookrangeview.md)|Gets some rows below a given range.|
|[Usedrange](../api/range-usedrange.md)|[Range](range.md)|Returns the used range of the given range object.|
|[Clear](../api/range-clear.md)|None|Clear range values, format, fill, border, etc.|
|[Delete](../api/range-delete.md)|None|Deletes the cells associated with the range.|
|[Insert](../api/range-insert.md)|[Range](range.md)|Inserts a cell or a range of cells into the worksheet in place of this range, and shifts the other cells to make space. Returns a new Range object at the now blank space.|
|[Merge](../api/range-merge.md)|None|Merge the range cells into one region in the worksheet.|
|[Resizedrange](../api/workbookrange-resizedrange.md)|[workbookRangeView](workbookrangeview.md)|Gets a range object similar to the current range object, but with its bottom-right corner expanded (or contracted) by some number of rows and columns.|
|[Unmerge](../api/range-unmerge.md)|None|Unmerge the range cells into separate cells.|
|[Visibleview](../api/workbookrange-visibleview.md)|[workbookRangeView](workbookrangeview.md)|Get the range visible from a filtered range.|

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|address|string|Represents the range reference in A1-style. Address value contains the Sheet reference (for example, Sheet1!A1:B4). Read-only.|
|addressLocal|string|Represents range reference for the specified range in the language of the user. Read-only.|
|cellCount|int|Number of cells in the range. Read-only.|
|columnCount|int|Represents the total number of columns in the range. Read-only.|
|columnHidden|boolean|Represents if all columns of the current range are hidden.|
|columnIndex|int|Represents the column number of the first cell in the range. Zero-indexed. Read-only.|
|formulas|Json|Represents the formula in A1-style notation.|
|formulasLocal|Json|Represents the formula in A1-style notation, in the user's language and number-formatting locale.  For example, the English "=SUM(A1, 1.5)" formula would become "=SUMME(A1; 1,5)" in German.|
|formulasR1C1|Json|Represents the formula in R1C1-style notation.|
|hidden|boolean|Represents if all cells of the current range are hidden. Read-only.|
|numberFormat|Json|Represents Excel's number format code for the given cell.|
|rowCount|int|Returns the total number of rows in the range. Read-only.|
|rowHidden|boolean|Represents if all rows of the current range are hidden.|
|rowIndex|int|Returns the row number of the first cell in the range. Zero-indexed. Read-only.|
|text|Json|Text values of the specified range. The Text value doesn't depend on the cell width. The # sign substitution that happens in Excel UI doesn't affect the text value returned by the API. Read-only.|
|valueTypes|Json|Represents the type of data of each cell. The possible values are: `Unknown`, `Empty`, `String`, `Integer`, `Double`, `Boolean`, `Error`. Read-only.|
|values|Json|Represents the raw values of the specified range. The data returned could be of type string, number, or a boolean. Cell that contains an error returns the error string.|

## Relationships
| Relationship | Type	|Description|
|:---------------|:--------|:----------|
|format|[WorkbookRangeFormat](rangeformat.md)|Returns a format object, encapsulating the range's font, fill, borders, alignment, and other properties. Read-only.|
|sort|[WorkbookRangeSort](rangesort.md)|The worksheet containing the current range. Read-only.|
|worksheet|[WorkbookWorksheet](worksheet.md)|The worksheet containing the current range. Read-only.|

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "baseType": "microsoft.graph.entity",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.workbookRange"
}-->

```json
{
  "address": "string",
  "addressLocal": "string",
  "cellCount": 1024,
  "columnCount": 1024,
  "columnHidden": true,
  "columnIndex": 1024,
  "formulas": "json",
  "formulasLocal": "json",
  "formulasR1C1": "json",
  "hidden": true,
  "numberFormat": "json",
  "rowCount": 1024,
  "rowHidden": true,
  "rowIndex": 1024,
  "text": "json",
  "valueTypes": "string",
  "values": "json"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Range resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

