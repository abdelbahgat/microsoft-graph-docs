---
title: "stringKeyLongValuePair resource type"
description: "Represents a key-value pair where the key is a string and the value is an Int64."
ms.localizationpriority: medium
doc_type: resourcePageType
author: "ArvindHarinder1"
ms.prod: "applications"
---

# stringKeyLongValuePair resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a key-value pair where the key is a string and the value is an Int64.

## Properties
| Property       | Type    |Description|
|:---------------|:--------|:----------|
|key|String| The mapping of the user type from the source system to the target system. For example:<br/><li>`User to User` - For Microsoft Entra ID to Microsoft Entra synchronization <br/><li>`worker to user` - For Workday to Microsoft Entra synchronization. <br/> |
|value|Int64|Total number of synchronized objects.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.stringKeyLongValuePair"
}-->

```json
{
  "key": "String",
  "value": "Integer"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "stringKeyLongValuePair resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
