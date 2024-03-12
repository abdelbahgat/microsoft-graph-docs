---
title: 'standardWebPart resource type'
description: Represents a standard web part instance on a SharePoint page.
author: sangle7
ms.localizationpriority: medium
ms.prod: sharepoint
doc_type: resourcePageType
---

# standardWebPart resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a standard web part instance on a SharePoint page.

Inherits from [webPart](../resources/webpart.md).

## Properties

| Property    | Type                                       | Description                                                                          |
| :---------- | :----------------------------------------- | :----------------------------------------------------------------------------------- |
| data        | [webPartData](../resources/webpartdata.md) | Data of the webPart.                                                                 |
| id          | String                                     | Instance identifier of the webPart. Inherited from [entity](../resources/entity.md). |
| webPartType | String                                     | A Guid which indicates the type of the webParts                                      |

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.standardWebPart",
  "baseType": "microsoft.graph.webPart",
  "openType": false
}
-->

```json
{
  "@odata.type": "#microsoft.graph.standardWebPart",
  "id": "String (identifier)",
  "webPartType": "String",
  "data": {
    "@odata.type": "microsoft.graph.webPartData"
  }
}
```
