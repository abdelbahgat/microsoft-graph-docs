---
title: "searchQuery resource type"
description: "searchQuery"
ms.localizationpriority: medium
author: "nmoreau"
ms.prod: "search"
doc_type: "resourcePageType"
---

# searchQuery resource type

Namespace: microsoft.graph

Represents a search query that contains search terms and optional filters.

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|queryString|String|The search query containing the search terms. Required.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.searchQuery",
  "baseType": null
}-->

```json
{
  "queryString": "String"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "searchQuery resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

