---
title: "unifiedRole resource type"
description: "The directory roles that can be assigned to a Microsoft partner through a delegated admin relationship."
author: "koravvams"
ms.localizationpriority: medium
ms.prod: partner-customer-administration
doc_type: resourcePageType
---

# unifiedRole resource type
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

The directory roles that can be assigned to a Microsoft partner through a delegated admin relationship.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|roleDefinitionId|String|The unified role definition ID of the directory role. Refer to [unifiedRoleDefinition](../resources/unifiedRoleDefinition.md) resource.|

## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.unifiedRole"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.unifiedRole",
  "roleDefinitionId": "String"
}
```

