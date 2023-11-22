---
title: "teamDiscoverySettings resource type"
description: "Settings to configure team discoverability by others."
ms.localizationpriority: medium
author: "nkramer"
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# teamDiscoverySettings resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Provides settings to enable others to configure [team](team.md) discoverability. You can only modify discovery settings for private teams.

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|showInTeamsSearchAndSuggestions|Boolean|If set to true, the team is visible via search and suggestions from the Teams client.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.teamDiscoverySettings"
}-->

```json
{
  "showInTeamsSearchAndSuggestions": true
}
```

<!-- uuid: f1d42106-0b3d-4930-9f19-d76f4e03b36b
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "team's discoverySettings resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->


