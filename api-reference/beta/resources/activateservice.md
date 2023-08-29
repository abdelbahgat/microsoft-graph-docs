---
title: "activateService resource type"
description: "Represents a service to be activated."
author: "dkershaw10"
ms.localizationpriority: medium
ms.prod: "directory-management"
doc_type: apiPageType
---

# activateService resource type (deprecated)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a service to be activated.

## Properties

| Property         | Type         | Description                           |
| ----------------- | ------------ | ------------------------------------- |
| service| String | The name of the service to activate. |
| servicePlanId | Guid | The plan identifier of the service plan to activate. |
| skuId | Guid | The SKU identifier of the service plan. |

## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.activateService"
}-->

```json
{
    "service": "String",
    "skuId": "Guid",
    "servicePlanId": "Guid"
}

```

<!-- uuid: 20fd7863-9545-40d4-ae8f-fee2d115a690
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "activateService",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
