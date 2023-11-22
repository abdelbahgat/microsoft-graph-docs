---
title: "educationIdentitySynchronizationConfiguration resource type"
description: "Abstract base class for all school data profile identity synchronization configurations. The derived classes define the behavior for synchronizing identities. The following are the derived types."
author: "mmast-msft"
ms.localizationpriority: medium
ms.prod: "education"
doc_type: resourcePageType
---

# educationIdentitySynchronizationConfiguration resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Abstract base class for all school data profile identity synchronization configurations. The derived classes define the behavior for synchronizing identities. The following are the derived types.

## Derived types

| Type                                                                                | Description                                                                         |
| :---------------------------------------------------------------------------------- | :---------------------------------------------------------------------------------- |
| [educationIdentityMatchingConfiguration](educationidentitymatchingconfiguration.md) | Use this type to **match existing** user accounts in Microsoft Entra ID. |
| [educationIdentityCreationConfiguration](educationidentitycreationconfiguration.md) | Use this type to **create new** user accounts in Microsoft Entra ID.                              |

## JSON representation

<!-- {
  "blockType": "resource",
   "isAbstract":true,
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationIdentitySynchronizationConfiguration"
}-->

```json
{}
```
