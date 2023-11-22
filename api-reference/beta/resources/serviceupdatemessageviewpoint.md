---
title: "serviceUpdateMessageViewpoint resource type"
description: Represents user view points data for a serviceUpdateMessage."
author: "payiAzure"
ms.localizationpriority: medium
ms.prod: "service-communications"
doc_type: resourcePageType
---

# serviceUpdateMessageViewpoint resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents user view points data for a [serviceUpdateMessage](../resources/serviceupdatemessage.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|isArchived|Boolean|Indicates whether the user archived the message.|
|isFavorited|Boolean|Indicates whether the user marked the message as favorite.|
|isRead|Boolean|Indicates whether the user read the message.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.serviceUpdateMessageViewpoint"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.serviceUpdateMessageViewpoint",
  "isRead": "Boolean",
  "isArchived": "Boolean",
  "isFavorited": "Boolean"
}
```
