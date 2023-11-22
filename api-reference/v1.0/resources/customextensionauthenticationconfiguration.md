---
title: "customExtensionAuthenticationConfiguration resource type"
description: "Abstract base type that exposes the configuration for the **authenticationConfiguration** property of the derived types that inherit from the customCalloutExtension abstract type"
author: "vikama-microsoft"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# customExtensionAuthenticationConfiguration resource type

Namespace: microsoft.graph

Abstract base type that exposes the configuration for the **authenticationConfiguration** property of the derived types that inherit from the [customCalloutExtension](customcalloutextension.md) abstract type.

This abstract type is inherited by the following resource type:

- [azureAdPopTokenAuthentication](../resources/azureAdPopTokenAuthentication.md)

The type of token authentication used depends on the token security. If the value is Proof of Possession, you'll use the [azureAdPopTokenAuthentication](../resources/azureAdPopTokenAuthentication.md) resource type.

## Properties

None.

## JSON representation

Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.customExtensionAuthenticationConfiguration",
  "abstract": true
}
-->

``` json
{ 
  "@odata.type": "#microsoft.graph.customExtensionAuthenticationConfiguration" 
} 
```
