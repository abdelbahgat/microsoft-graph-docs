---
title: "convertIdResult resource type"
description: "The result of an ID format conversion performed by the translateExchangeIds function."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "outlook"
author: "SuryaLashmiS"
---

# convertIdResult resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The result of an ID format conversion performed by the [translateExchangeIds](../api/user-translateexchangeids.md) function.

## Properties

| Property | Type | Description |
|:---------|:-----|:------------|
| sourceId | String | The identifier that was converted. This value is the original, unconverted identifier. |
| targetId | String | The converted identifier. This value isn't present if the conversion failed. |
| errorDetails | [genericError](genericerror.md) | An error object indicating the reason for the conversion failure. This value isn't present if the conversion succeeded. |

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "targetId",
    "errorDetails"
  ],
  "@odata.type": "microsoft.graph.convertIdResult"
}-->

```json
{
  "sourceId": "String",
  "targetId": "String",
  "errorDetails": {
    "@odata.type": "microsoft.graph.genericError"
  }
}
```


