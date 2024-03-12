---
title: "tabUpdatedEventMessageDetail resource type"
description: "Represents the details of an event message about an updated tab."
author: "RamjotSingh"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# tabUpdatedEventMessageDetail resource type

Namespace: microsoft.graph

Represents the details of an event message about an updated tab.
This message is generated when a tab is updated in a [channel](../resources/channel.md) or a [chat](../resources/chat.md).


Inherits from [eventMessageDetail](../resources/eventmessagedetail.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|initiator|[identitySet](../resources/identityset.md)|Initiator of the event.|
|tabId|String|Unique identifier of the tab.|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.tabUpdatedEventMessageDetail",
  "baseType": "microsoft.graph.eventMessageDetail"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.tabUpdatedEventMessageDetail",
  "tabId": "String",
  "initiator": {
    "@odata.type": "microsoft.graph.identitySet"
  }
}
```


## See also
- [Example response for an event message about an updated tab](/graph/system-messages/#tab-updated)
- For more information about other types of events, see [System messages](/graph/system-messages).
