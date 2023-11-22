---
title: "cloudRealtimeCommunicationInfo resource type"
description: "Microsoft real-time communication information related to the user."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "directory-management"
author: "rungari"
---

# cloudRealtimeCommunicationInfo resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a group of properties that relate to Microsoft real-time communication information for a user.

## Properties

| Property                    | Type     | Description                                                                                      |
| --------------------------- | -------- | ------------------------------------------------------------------------------------------------ |
| isSipEnabled                | Boolean  | Indicates whether the user has a SIP-enabled client registered for them. Read-only.              |

## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.cloudRealtimeCommunicationInfo"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.cloudRealtimeCommunicationInfo",
  "isSipEnabled": "Boolean"
}
```
