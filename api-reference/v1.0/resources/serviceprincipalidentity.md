---
title: "servicePrincipalIdentity resource type"
description: "Models a service principal identity."
author: "jyothig123"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# servicePrincipalIdentity resource type

Namespace: microsoft.graph

Models a service principal identity.

Inherits from [identity](../resources/identity.md).

## Properties
|Property|Type|Description|
|:---|:---|:---|
|appId|String|The application identifier of the service principal.|
|displayName|String|The display name of the service principal identity. Inherited from [identity](../resources/identity.md)|
|id|String|The identifier of the service principal identity. Inherited from [identity](../resources/identity.md)|

## Relationships
None.

## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.servicePrincipalIdentity"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.servicePrincipalIdentity",
  "id": "String (identifier)",
  "displayName": "String",
  "appId": "String"
}
```
