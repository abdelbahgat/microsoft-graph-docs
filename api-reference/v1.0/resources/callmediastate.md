---
title: "callMediaState resource type"
description: "Represents the media state for a call."
author: "ananmishr"
ms.prod: "cloud-communications"
ms.localizationpriority: medium
doc_type: resourcePageType
---

# callMediaState resource type

Namespace: microsoft.graph


Represents the media state for a [call](call.md).

## Properties

| Property            | Type    | Description                                                                    |
|:--------------------|:--------|:-------------------------------------------------------------------------------|
| audio           | mediaState  | The audio media state. Possible values are: `active`, `inactive`, `unknownFutureValue`. |

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.callMediaState"
}-->
```json
{
  "audio": "active | inactive",
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "callMediaState resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

