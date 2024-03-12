---
title: "teamJoiningDisabledEventMessageDetail resource type"
description: "Represents the details of an event message about team joining disabled."
author: "RamjotSingh"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# teamJoiningDisabledEventMessageDetail resource type

Namespace: microsoft.graph

Represents the details of an event message about [team](../resources/team.md) joining disabled.
This message is generated when joining is disabled for a **team**.


Inherits from [eventMessageDetail](../resources/eventmessagedetail.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|initiator|[identitySet](../resources/identityset.md)|Initiator of the event.|
|teamId|String|Unique identifier of the **team**.|
## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.teamJoiningDisabledEventMessageDetail",
  "baseType": "microsoft.graph.eventMessageDetail"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.teamJoiningDisabledEventMessageDetail",
  "teamId": "String",
  "initiator": {
    "@odata.type": "microsoft.graph.identitySet"
  }
}
```


## See also
- [Example response for an event message about **team** joining disabled](/graph/system-messages/#team-joining-disabled)
- For more information about other types of events, see [System messages](/graph/system-messages).
