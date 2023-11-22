---
title: "emailAuthenticationMethodConfiguration resource type"
description: "Represents an email OTP authentication methods policy"
author: "tilarso"
ms.reviewer: intelligentaccesspm
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: "resourcePageType"
---

# emailAuthenticationMethodConfiguration resource type

Namespace: microsoft.graph

Represents this tenant's email OTP authentication methods policy. Authentication methods policies define configuration settings and users or groups who are enabled to use the authentication method. The tenant's cloud-native users may use email OTP for self-service password reset. External users may use email OTP for authentication during invitation redemption and self-service sign up for specific apps in user flows.

Inherits from [authenticationMethodConfiguration](../resources/authenticationmethodconfiguration.md).

## Methods

|Method|Return type|Description|
|:---|:---|:---|
|[Get emailAuthenticationMethodConfiguration](../api/emailauthenticationmethodconfiguration-get.md)|[emailAuthenticationMethodConfiguration](../resources/emailauthenticationmethodconfiguration.md)|Read the properties and relationships of an emailAuthenticationMethodConfiguration object.|
|[Update emailAuthenticationMethodConfiguration](../api/emailauthenticationmethodconfiguration-update.md)|[emailAuthenticationMethodConfiguration](../resources/emailauthenticationmethodconfiguration.md)|Update the properties of an emailAuthenticationMethodConfiguration object.|
|[Delete emailAuthenticationMethodConfiguration](../api/emailauthenticationmethodconfiguration-delete.md)|None|Deletes an emailAuthenticationMethodConfiguration object.|

## Properties

|Property|Type|Description|
|:---|:---|:---|
|allowExternalIdToUseEmailOtp|externalEmailOtpState|Determines whether email OTP is usable by external users for authentication. Possible values are: `default`, `enabled`, `disabled`, `unknownFutureValue`. Tenants in the `default` state who didn't use public preview have email OTP enabled beginning in October 2021.|
|excludeTargets|[excludeTarget](../resources/excludetarget.md) collection|Groups of users that are excluded from the policy.|
|id|String|The authentication method policy identifier. Inherited from [authenticationMethodConfiguration](../resources/authenticationmethodconfiguration.md).|
|state|authenticationMethodState|Indicates whether this authentication method is enabled or not. Possible values are: `enabled`, `disabled`.|

## Relationships

|Relationship|Type|Description|
|:---|:---|:---|
|includeTargets|[authenticationMethodTarget](../resources/authenticationmethodtarget.md) collection|A collection of groups that are enabled to use the authentication method.|

## JSON representation

Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.emailAuthenticationMethodConfiguration",
  "baseType": "microsoft.graph.authenticationMethodConfiguration",
  "openType": false
}
-->

```json
{
  "@odata.type": "#microsoft.graph.emailAuthenticationMethodConfiguration",
  "allowExternalIdToUseEmailOtp": "String",
  "excludeTargets": [
    {
      "@odata.type": "microsoft.graph.excludeTarget"
    }
  ],
  "id": "String (identifier)",
  "includeTargets": [ { "@odata.type": "microsoft.graph.authenticationMethodTarget" } ],
  "state": "String"
}
```
