---
title: "clientCertificateAuthentication resource type"
description: "Represents the configuration for retrieving a clientCertificateAuthentication."
author: "nickgmicrosoft"
ms.localizationpriority: medium
ms.prod: "identity-and-sign-in"
doc_type: resourcePageType
---

# clientCertificateAuthentication resource type

Namespace: microsoft.graph

A type derived from apiAuthenticationConfigurationBase that is used to represent a Pkcs12-based client certificate authentication. This is used to retrieve the public properties of uploaded certificates.

Inherits from [apiAuthenticationConfigurationBase](../resources/apiauthenticationconfigurationbase.md).

## Properties

|Property|Type|Description|
|:---|:---|:---|
|certificateList| [pkcs12CertificateInformation](../resources/pkcs12CertificateInformation.md) collection| The list of certificates uploaded for this API connector.|

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.clientCertificateAuthentication"
}
-->

``` json
{
  "@odata.type": "#microsoft.graph.clientCertificateAuthentication",
  "certificateList": "Collection(microsoft.graph.pkcs12CertificateInformation)",
}
```
