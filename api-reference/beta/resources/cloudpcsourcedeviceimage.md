---
title: "cloudPcSourceDeviceImage resource type"
description: "The source image associated with your Azure subscription. "
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: resourcePageType
---

# cloudPcSourceDeviceImage resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The source image associated with your Azure subscription.

## Properties

|Property|Type|Description|
|:---|:---|:---|
|id|String|The ID of the source image.|
|displayName|String|The display name for the source image.|
|subscriptionId|String|The ID of subscription that hosts the source image.|
|subscriptionDisplayName|String|The display name of subscription that hosts the source image.|

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.cloudPcSourceDeviceImage"
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.cloudPcSourceDeviceImage",
  "id": "String (identifier)",
  "displayName": "String",
  "subscriptionId": "String",
  "subscriptionDisplayName": "String"
}
```
