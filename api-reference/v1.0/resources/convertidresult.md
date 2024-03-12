---
title: "convertIdResult resource type"
description: "The result of an ID format conversion performed by the translateExchangeIds function."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "outlook"
author: "abheek-das"
---

# convertIdResult resource type

Namespace: microsoft.graph

The result of an ID format conversion performed by the [translateExchangeIds](../api/user-translateexchangeids.md) function.

## Properties

| Property | Type | Description |
|:---------|:-----|:------------|
| errorDetails | [genericError](genericerror.md) | An error object indicating the reason for the conversion failure. This value is not present if the conversion succeeded. |
| sourceId | String | The identifier that was converted. This value is the original, un-converted identifier. |
| targetId | String | The converted identifier. This value is not present if the conversion failed. |

## JSON representation

Here is a JSON representation of the resource.

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
  "errorDetails": {
    "@odata.type": "microsoft.graph.genericError"
  },
  "sourceId": "String",
  "targetId": "String"
}
```

