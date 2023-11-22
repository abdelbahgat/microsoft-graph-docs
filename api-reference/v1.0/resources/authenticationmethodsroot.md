---
title: "authenticationMethodsRoot resource type"
description: "Container for navigation properties of resources for Microsoft Entra authentication methods."
author: "kvenkit"
ms.localizationpriority: medium
ms.prod: "identity-and-access-reports"
doc_type: resourcePageType
---

# authenticationMethodsRoot resource type

Namespace: microsoft.graph

Container for navigation properties of resources for Microsoft Entra authentication methods.

Inherits from [entity](../resources/entity.md).

## Methods

None.

## Properties

|Property|Type|Description|
|:---|:---|:---|
|id|String| The unique identifier. Inherited from [entity](../resources/entity.md).|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|userRegistrationDetails|[userRegistrationDetails](../resources/userregistrationdetails.md)| Represents the state of a user's authentication methods, including which methods are registered and which features the user is registered and capable of (such as multifactor authentication, self-service password reset, and passwordless authentication).|

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.authenticationMethodsRoot",
  "baseType": "microsoft.graph.entity",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.authenticationMethodsRoot",
  "id": "String (identifier)"
}
```
