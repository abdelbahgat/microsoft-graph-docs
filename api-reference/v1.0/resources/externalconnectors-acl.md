---
title: "acl resource type"
description: "An access control entry for an item indexed by a Microsoft Search externalConnection."
author: "mecampos"
ms.localizationpriority: medium
ms.prod: "search"
doc_type: resourcePageType
---

# acl resource type

Namespace: microsoft.graph.externalConnectors

An access control entry for an item indexed by a Microsoft Search externalConnection.

## Properties
|Property|Type|Description|
|:---|:---|:---|
|accessType|microsoft.graph.externalConnectors.accessType|The access granted to the identity. Possible values are: `grant`, `deny`, `unknownFutureValue`.|
|type|microsoft.graph.externalConnectors.aclType|The type of identity. Possible values are: `user`, `group`, `everyone`, `everyoneExceptGuests`, `externalGroup`, `unknownFutureValue`.|
|value|String|The unique identifer of the identity. For Microsoft Entra identities, `value` is set to the object identifier of the user, group or tenant for types user, group and everyone (and everyoneExceptGuests) respectively. For external groups `value` is set to the ID of the externalGroup |

## Relationships
None.

## JSON representation
Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.externalConnectors.acl"
}
-->
``` json
{
  "accessType": "String",
  "type": "String",
  "value": "String"
}
```
