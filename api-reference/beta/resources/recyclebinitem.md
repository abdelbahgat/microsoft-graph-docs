---
author: "vanshisingh"
title: "recycleBinItem resource type"
description: "Represents information about a deleted item in a recycleBin."
ms.localizationpriority: "medium"
ms.prod: "sharepoint"
doc_type: apiPageType
---

# recycleBinItem resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents information about a deleted item in a [recycleBin](recyclebin.md) of a SharePoint [site](site.md).

Inherits from [baseItem](baseitem.md).

## Methods

| Method                                                  | Return Type                                                 | Description                                                                              |
|:--------------------------------------------------------|:------------------------------------------------------------|:-----------------------------------------------------------------------------------------|
| [List recycleBinItems](../api/recyclebin-list-items.md) | [recycleBinItem](../resources/recyclebinitem.md) collection |Get a list of [recycleBinItems](../resources/recyclebinitem.md) under the specified site. |

## Properties

| Property            | Type           | Description                                                                                                                                                                                                      |
|:--------------------|:---------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| deletedDateTime     | DateTimeOffset | Date and time when the item was deleted. The timestamp type represents date and time information using ISO 8601 format and is always in UTC. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. |
| deletedFromLocation | String         | Relative URL of the list or folder that originally contained the item.                                                                                                                                           |
| id                  | String         | Unique identifier of the delete transaction. Inherited from [baseItem](baseitem.md).                                                                                                                             |
| name                | String         | Name of the item. Inherited from [baseItem](baseitem.md).                                                                                                                                                        |
| size                | Int64          | Size of the item in bytes.                                                                                                                                                                                       |

## JSON Representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "baseType": "microsoft.graph.baseItem",
  "@odata.type": "microsoft.graph.recycleBinItem",
  "optionalProperties": []
}-->

```json
{
  "deletedDateTime": "String (timestamp)",
  "deletedFromLocation": "String",
  "id": "String (identifier)",
  "name": "String",
  "size": "Int64"
}
```

<!-- {
"type": "#page.annotation",
"description": "The recycleBinItem resource returns information about a deletion event and its associated resources.",
"keywords": "recycle,bin,recyclebin,delete ",
"createdBy": "API Clinic",
"section": "documentation"
}-->
