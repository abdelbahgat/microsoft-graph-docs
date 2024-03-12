---
author: JeremyKelley
description: The sharedDriveItem resource is returned when using the Shares API to access a shared driveItem.
ms.date: 09/10/2017
title: SharedDriveItem
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: files
---

# SharedDriveItem resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The **sharedDriveItem** resource is returned when using the [Shares](../api/shares-get.md) API to access a shared [driveItem](driveitem.md).

## JSON representation

Here is a JSON representation of the **sharedDriveItem** resource.

The **sharedDriveItem** resource is derived from [**baseItem**](baseitem.md) and inherits properties from that resource.

<!-- {
  "blockType": "resource",
  "baseType": "microsoft.graph.baseItem",
  "optionalProperties": [  ],
  "@odata.type": "microsoft.graph.sharedDriveItem"
}-->

```json
{
  "id": "string",
  "name": "string",
  "owner": { "@odata.type": "microsoft.graph.identitySet" },

  "driveItem": { "@odata.type": "microsoft.graph.driveItem" },
  "items": [ { "@odata.type": "microsoft.graph.driveItem" }],
  "list": { "@odata.type": "microsoft.graph.list" },
  "listItem": { "@odata.type": "microsoft.graph.listItem" },
  "permission": { "@odata.type": "microsoft.graph.permission" },
  "root": { "@odata.type": "microsoft.graph.driveItem" },
  "site": { "@odata.type": "microsoft.graph.site" }
}
```

## Properties

| Property | Type                          | Description                                                      |
| :------- | :---------------------------- | :--------------------------------------------------------------- |
| id       | String                        | The unique identifier for the share being accessed.              |
| name     | String                        | The display name of the shared item.                             |
| owner    | [IdentitySet](identityset.md) | Information about the owner of the shared item being referenced. |

## Relationships

| Relationship   | Type                         | Description                                                                |
| -------------- | :--------------------------- | :------------------------------------------------------------------------- |
| **driveItem**  | [**driveItem**][driveItem]   | Used to access the underlying **driveItem**                                |
| **list**       | [**list**][list]             | Used to access the underlying **list**                                     |
| **listItem**   | [**listItem**][listItem]     | Used to access the underlying **listItem**                                 |
| **permission** | [**permission**][permission] | Used to access the **permission** representing the underlying sharing link |
| **site**       | [**site**][site]             | Used to access the underlying **site**                                     |

Alternatively, for **driveItems** shared from personal OneDrive accounts, the following relationships may also be used.

| Relationship name | Type                                  | Description                                                                         |
| ----------------- | :------------------------------------ | :---------------------------------------------------------------------------------- |
| **items**         | [**driveItem**][driveItem] collection | All driveItems contained in the sharing root. This collection cannot be enumerated. |
| **driveItem**     | [**driveItem**][driveItem]            | Used to access the underlying **driveItem**                                         |

[driveItem]: driveitem.md
[list]: list.md
[listItem]: listitem.md
[permission]: permission.md
[site]: site.md

## Methods

| Method                                  | REST Path                |
| :-------------------------------------- | :----------------------- |
| [Get shared item](../api/shares-get.md) | `GET /shares/{share-id}` |

## Remarks

For more information about the facets on a DriveItem, see [DriveItem](driveitem.md).

<!--
{
  "type": "#page.annotation",
  "description": "Share resource returns information about a shared item or collection of items.",
  "keywords": "share,shared,sharing root,shared files, shared items",
  "section": "documentation",
  "tocPath": "Resources/Share",
  "suppressions": []
}
-->
