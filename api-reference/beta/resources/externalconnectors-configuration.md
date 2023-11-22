---
title: "configuration resource type"
description: "Specifies additional application IDs that are allowed to manage the externalConnection and to index content in a externalConnection."
ms.localizationpriority: medium
author: "snlraju-msft"
ms.prod: "search"
doc_type: "resourcePageType"
---

# configuration resource type

Namespace: microsoft.graph.externalConnectors

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Specifies additional application IDs that are allowed to manage the externalConnection and to index content in a [externalConnection](../resources/externalconnectors-externalconnection.md).

## Properties

| Property       | Type              | Description |
|:---------------|:------------------|:------------|
| authorizedAppIds | String collection | A collection of application IDs for registered Microsoft Entra apps that are allowed to manage the externalConnection and to index content in the externalConnection. |

> [!NOTE]
> The `authorizedAppIds` property was previously named `authorizedApps`.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.externalConnectors.configuration",
  "baseType": null
}-->

```json
{
  "authorizedAppIds": ["String"]
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "configuration resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
