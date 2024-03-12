---
title: "channelRenamedEventMessageDetail resource type"
description: "Represents the details of an event message about a renamed channel."
author: "RamjotSingh"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# channelRenamedEventMessageDetail resource type

Namespace: microsoft.graph

Represents the details of an event message about a renamed [channel](../resources/channel.md).
This message is generated when a **channel's** name is updated.


Inherits from [eventMessageDetail](../resources/eventmessagedetail.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|channelDisplayName|String|The updated name of the **channel**.|
|channelId|String|Unique identifier of the **channel**.|
|initiator|[identitySet](../resources/identityset.md)|Initiator of the event.|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.channelRenamedEventMessageDetail",
  "baseType": "microsoft.graph.eventMessageDetail"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.channelRenamedEventMessageDetail",
  "channelDisplayName": "String",
  "initiator": {
    "@odata.type": "microsoft.graph.identitySet"
  },
  "channelId": "String"
}
```


## See also
- [Example response for an event message about a renamed **channel**](/graph/system-messages/#channel-renamed)
- For more information about other types of events, see [System messages](/graph/system-messages).
