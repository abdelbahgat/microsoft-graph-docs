---
title: "pkcs12Certificate resource type"
description: "Represents the configuration for uploading a pkcs12Certificate."
author: "nickgmicrosoft"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# pkcs12Certificate resource type

Namespace: microsoft.graph

Represents the configuration used to upload a certificate when using HTTPS client-certificate authentication for calling an API connector endpoint. Client certificate authentication is a mutual certificate-based authentication, where the client provides a client certificate to an API endpoint to prove its identity. Microsoft Entra ID sends the configured certificate to the given API endpoint, which then validates the certificate.

Inherits from [apiAuthenticationConfigurationBase](../resources/apiauthenticationconfigurationbase.md).

## Properties

|Property|Type|Description|
|:---|:---|:---|
|password|String| The password for the pfx file. Required. If no password is used, you must still provide a value of `""`.|
|pkcs12Value|String| Represents the pfx content that is sent. The value should be a base-64 encoded version of the actual certificate content. Required.|

## JSON representation

Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.pkcs12Certificate"
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.pkcs12Certificate",
  "pkcs12Value": "String",
  "password": "String"
}
```
