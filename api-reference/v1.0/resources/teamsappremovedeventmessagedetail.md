---
title: "teamsAppRemovedEventMessageDetail resource type"
description: "Represents the details of an event message about teamsApp removed."
author: "RamjotSingh"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# teamsAppRemovedEventMessageDetail resource type

Namespace: microsoft.graph

Represents the details of an event message about [teamsApp](../resources/teamsApp.md) removed.
This message is generated when a **teamsApp** is removed from a [channel](../resources/channel.md), a [chat](../resources/chat.md), or a [team](../resources/team.md).


Inherits from [eventMessageDetail](../resources/eventmessagedetail.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|initiator|[identitySet](../resources/identityset.md)|Initiator of the event.|
|teamsAppDisplayName|String|Display name of the **teamsApp**.|
|teamsAppId|String|Unique identifier of the **teamsApp**.|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.teamsAppRemovedEventMessageDetail",
  "baseType": "microsoft.graph.eventMessageDetail"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.teamsAppRemovedEventMessageDetail",
  "teamsAppId": "String",
  "teamsAppDisplayName": "String",
  "initiator": {
    "@odata.type": "microsoft.graph.identitySet"
  }
}
```


## See also
- [Example response for an event message about **teamsApp** removed](/graph/system-messages/#teams-app-removed)
- For more information about other types of events, see [System messages](/graph/system-messages).
