---
title: "builtInIdentityProvider resource type"
description: "Represents built-in identity providers in a Microsoft Entra tenant."
ms.localizationpriority: high
doc_type: resourcePageType
ms.prod: "identity-and-sign-in"
author: "namkedia"
---

# builtInIdentityProvider resource type
Namespace: microsoft.graph

Represents built-in identity providers with [External Identities](/azure/active-directory/external-identities/) for a Microsoft Entra tenant.

For Microsoft Entra B2B scenarios in a Microsoft Entra tenant, the built-in identity provider type can be a Microsoft Entra ID, Microsoft account(MSA) or email one-time passcode (EmailOTP).

This type inherits from [identityProviderBase](../resources/identityproviderbase.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[List](../api/identitycontainer-list-identityproviders.md)|[identityProviderBase](../resources/identityproviderbase.md) collection|Retrieve all identity providers configured in a tenant including the built-in identity providers. There's no way to retrieve only the built-in identity providers in a tenant.|
|[Get](../api/identityproviderbase-get.md) |builtInIdentityProvider|Retrieve properties of a built-in identity provider.|
|[List available provider types](../api/identityproviderbase-availableprovidertypes.md)|String collection|Retrieve all available identity provider types available in the tenant.|

## Properties

|Property|Type|Description|
|:---------------|:--------|:----------|
|displayName|String|The display name of the identity provider. Inherited from [identityProviderBase](../resources/identityproviderbase.md).|
|id|String|The identifier of the identity provider. Inherited from [identityProviderBase](../resources/identityproviderbase.md). Read-only.|
|identityProviderType|String|The identity provider type. For a B2B scenario, possible values: `AADSignup`, `MicrosoftAccount`, `EmailOTP`. Required.|

## JSON representation

Here's a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.builtInIdentityProvider"
} -->

```json
{
    "displayName": "String",
    "id": "String",
    "identityProviderType": "String"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2021-03-30 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
 "description": "builtinIdentityProvider",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
