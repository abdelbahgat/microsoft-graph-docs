---
title: "directorySizeQuota resource type"
description: "Represents a company's used and total directory quota."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "directory-management"
author: "adimitui"
---

# directorySizeQuota resource type

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a company's used and total directory quota.

## Properties
| Property   | Type|Description|
|:---------------|:--------|:----------|
|used|Int32| Used amount of the directory quota. |
|total|Int32| Total amount of the directory quota.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.directorySizeQuota"
}-->

```json
{
  "used": "Int32",
  "total": "Int32"
}
```
