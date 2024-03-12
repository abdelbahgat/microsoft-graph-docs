---
title: "addIn resource type"
description: "Here is a JSON representation of the resource."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "applications"
author: "sureshja"
---

# addIn resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Defines custom behavior that a consuming service can use to call an app in specific contexts. For example, applications that can render file streams [might configure add-ins](/onedrive/developer/file-handlers/?view=odsp-graph-online&preserve-view=true) for File Handler functionality. This will let services like Microsoft 365 call the application in the context of a document the user is working on.

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|id|guid||
|properties|[keyValue](keyvalue.md) collection||
|type|string||

## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.addIn"
}-->

```json
{
  "id": "GUID",
  "properties": [{"@odata.type": "microsoft.graph.keyValue"}],
  "type": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "addIn resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
