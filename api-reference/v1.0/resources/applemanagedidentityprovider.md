---
title: "appleManagedIdentityProvider resource type"
description: "Represents the Apple identity provider in an Azure AD B2C tenant."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "identity-and-sign-in"
author: "namkedia"
---

# appleManagedIdentityProvider resource type
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents the Apple identity provider in an Azure AD B2C tenant.

You can configure Apple as a social identity provider for an Azure AD B2C tenant. Based on the information Apple provides, the API will generate a client secret. Apple needs the secret to be renewed every six months. You will have to manually rotate the secret.

Inherits from [identityProviderBase](../resources/identityproviderbase.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[List](../api/identitycontainer-list-identityproviders.md)|[identityProviderBase](../resources/identityproviderbase.md) collection|Retrieve all identity providers configured in a tenant, including the Apple identity providers. There is no way to retrieve only the Apple identity providers in a tenant.|
|[Create](../api/identitycontainer-post-identityproviders.md)|[appleManagedIdentityProvider](../resources/applemanagedidentityprovider.md) |Create a new Apple identity provider configuration.|
|[Get](../api/identityproviderbase-get.md) |[appleManagedIdentityProvider](../resources/applemanagedidentityprovider.md) |Retrieve properties of the Apple identity provider configuration.|
|[Update](../api/identityproviderbase-update.md)|None|Update the Apple identity provider configuration.|
|[Delete](../api/identityproviderbase-delete.md)|None|Delete the Apple identity provider configuration.|
|[List available provider types](../api/identityproviderbase-availableprovidertypes.md)|String collection|Retrieve all available identity provider types available in the tenant.|

## Properties

|Property|Type|Description|
|:---------------|:--------|:----------|
|certificateData|String|The certificate data, which is a long string of text from the certificate. Can be null.|
|developerId|String|The Apple developer identifier. Required.|
|displayName|String|The display name of the identity provider. Inherited from [identityProviderBase](../resources/identityproviderbase.md).|
|id|String|The identifier of the identity provider. Inherited from [identityProviderBase](../resources/identityproviderbase.md). Read-only.|
|keyId|String|The Apple key identifier. Required.|
|serviceId|String|The Apple service identifier. Required.|

Retrieve the **developerId**, **serviceId**, **keyId**, and the **certificateData** from the Apple developer portal. For more information, follow the guide to [create an Apple ID application](/azure/active-directory-b2c/identity-provider-apple-id?pivots=b2c-user-flow#create-an-apple-id-application).

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.appleManagedIdentityProvider"
} -->

```json
{
    "id": "String",
    "displayName": "String",
    "developerId": "String",
    "serviceId": "String",
    "keyId": "String",
    "certificateData": "String"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2021-03-30 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
 "description": "appleIdentityProvider",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
