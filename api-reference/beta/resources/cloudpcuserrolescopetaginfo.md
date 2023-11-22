---
title: "cloudPcUserRoleScopeTagInfo resource type"
description: "Represents the scope tag info with display name and identity."
author: "ecmadao"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: resourcePageType
---

# cloudPcUserRoleScopeTagInfo resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents the scope tag info with display name and identity.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|displayName|String|Scope tag display name.|
|roleScopeTagId|String|Scope tag ID.|

## Relationships

None

## JSON Representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.cloudPcUserRoleScopeTagInfo"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.cloudPcUserRoleScopeTagInfo",
  "displayName": "String",
  "roleScopeTagId": "String"
}
```
