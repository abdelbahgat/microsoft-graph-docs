---
title: "openIdConnectIdentityProvider resource type"
description: "Represents OpenIDConnect identity providers in an Azure Active Directory B2C tenant."
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "identity-and-sign-in"
author: "namkedia"
---

# openIdConnectIdentityProvider resource type
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents OpenID Connect identity providers in an Azure Active Directory (Azure AD) B2C tenant.

Configuring an OpenID Connect provider in an Azure AD B2C tenant enables users to sign up and sign in to any application using their custom identity provider.

Inherits from [identityProviderBase](../resources/identityproviderbase.md).

## Methods

| Method       | Return Type  |Description|
|:---------------|:--------|:----------|
|[List](../api/identitycontainer-list-identityproviders.md)|[identityProviderBase](../resources/identityproviderbase.md)  collection|Retrieve all identity providers configured in a tenant including the [openIdConnectIdentityProvider](../resources/openidconnectidentityprovider.md) object type. There is no way to retrieve only the OpenID Connect identity providers in a tenant.|
|[Create](../api/identitycontainer-post-identityproviders.md)|[openIdConnectIdentityProvider](../resources/openidconnectidentityprovider.md)|Create a new [openIdConnectIdentityProvider](../resources/openidconnectidentityprovider.md) object.|
|[Get](../api/identityproviderbase-get.md) |openIdConnectIdentityProvider|Retrieve properties of an [openIdConnectIdentityProvider](../resources/openidconnectidentityprovider.md) object.|
|[Update](../api/identityproviderbase-update.md)|None|Update an [openIdConnectIdentityProvider](../resources/openidconnectidentityprovider.md) object.|
|[Delete](../api/identityproviderbase-delete.md)|None|Delete an [openIdConnectIdentityProvider](../resources/openidconnectidentityprovider.md) object.|
|[List available provider types](../api/identityproviderbase-availableprovidertypes.md)|String collection|Retrieve all available identity provider types available in the tenant.|

## Properties

|Property|Type|Description|
|:---------------|:--------|:----------|
|clientId|String|The client identifier for the application obtained when registering the application with the identity provider. Required.|
|clientSecret|String|The client secret for the application obtained when registering the application with the identity provider. The clientSecret has a dependency on **responseType**. <ul><li>When **responseType** is `code`, a secret is required for the auth code exchange.</li><li>When **responseType** is `id_token` the secret is not required because there is no code exchange. The id_token is returned directly from the authorization response.</li></ul> This is write-only. A read operation returns `****`.|
|id|String|The identifier of the identity provider.Required. Inherited from [identityProviderBase](../resources/identityproviderbase.md). Read-only.|
|displayName|String|The display name of the identity provider. |
|claimsMapping|[claimsMapping](claimsmapping.md)|After the OIDC provider sends an ID token back to Azure AD, Azure AD needs to be able to map the claims from the received token to the claims that Azure AD recognizes and uses. This complex type captures that mapping. Required.|
|domainHint|String|The domain hint can be used to skip directly to the sign-in page of the specified identity provider, instead of having the user make a selection among the list of available identity providers.|
|metadataUrl|String|The URL for the metadata document of the OpenID Connect identity provider. Every OpenID Connect identity provider describes a metadata document that contains most of the information required to perform sign-in. This includes information such as the URLs to use and the location of the service's public signing keys. The OpenID Connect metadata document is always located at an endpoint that ends in `.well-known/openid-configuration`. Provide the metadata URL for the OpenID Connect identity provider you add. Read-only. Required.|
|responseMode|[openIdConnectResponseMode](#openidconnectresponsemode-values)|The response mode defines the method used to send data back from the custom identity provider to Azure AD B2C. Possible values: `form_post`, `query`. Required.|
|responseType|[openIdConnectResponseTypes](#openidconnectresponsetypes-values)|The response type describes the type of information sent back in the initial call to the authorization_endpoint of the custom identity provider. Possible values: `code` , `id_token` , `token`.  Required.|
|scope|String|Scope defines the information and permissions you are looking to gather from your custom identity provider. OpenID Connect requests must contain the openid scope value in order to receive the ID token from the identity provider. Without the ID token, users are not able to sign in to Azure AD B2C using the custom identity provider. Other scopes can be appended, separated by a space. For more details about the scope limitations see [RFC6749 Section 3.3](https://tools.ietf.org/html/rfc6749#section-3.3). Required.|

### openIdConnectResponseMode values
|Member|Description|
:--------|:----------|
|form_post|This response mode is recommended for best security. The response is transmitted via the HTTP POST method, with the code or token being encoded in the body using the application/x-www-form-urlencoded format.|
|query|The code or token is returned as a query parameter.|
|unknownFutureValue|A sentinel value to indicate future values.|

### openIdConnectResponseTypes values
|Member|Description|
:--------|:----------|
|code|As per the authorization code flow, a code will be returned back to Azure AD B2C. Azure AD B2C proceeds to call the token_endpoint to exchange the code for the token.|
|id_token|An ID token is returned back to Azure AD B2C from the custom identity provider.|
|token|An access token is returned back to Azure AD B2C from the custom identity provider. (This value is not supported by Azure AD B2C at the moment)|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.openIdConnectIdentityProvider",
  "baseType": "microsoft.graph.identityProviderBase",
} -->

```json
{
  "@odata.type": "#microsoft.graph.openIdConnectIdentityProvider",
  "id": "String (identifier)",
  "displayName": "String",
  "clientId": "String",
  "clientSecret": "String",
  "scope": "String",
  "metadataUrl": "String",
  "domainHint": "String",
  "responseType": "String",
  "responseMode": "String",
  "claimsMapping": {
    "@odata.type": "microsoft.graph.claimsMapping"
  }
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2021-03-30 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
 "description": "openidconnectIdentityProvider",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
