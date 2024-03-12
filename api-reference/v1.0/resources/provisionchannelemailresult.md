---
title: "provisionChannelEmailResult resource type"
description: "Represents the result of a channel email provisioning operation."
author: "anandab-msft"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# provisionChannelEmailResult resource type

Namespace: microsoft.graph

Represents the email address [provisioned](..\api\channel-provisionemail.md) for a [channel](channel.md).

## Properties
| Property | Type   | Description                               |
| :------- | :----- | :---------------------------------------- |
| email    | String | Represents the provisioned email address. |

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.provisionChannelEmailResult"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.provisionChannelEmailResult",
  "email": "String"
}
```
