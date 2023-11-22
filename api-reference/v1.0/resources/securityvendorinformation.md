---
title: "securityVendorInformation resource type"
description: " subProvider=AppLocker)."
ms.localizationpriority: medium
author: "preetikr"
ms.prod: "security"
doc_type: resourcePageType
---

# securityVendorInformation resource type

Namespace: microsoft.graph

Contains details about the security product/service vendor, provider, and subprovider (for example, vendor=Microsoft; provider=Windows Defender ATP; subProvider=AppLocker).

## Properties

| Property   | Type|Description|
|:---------------|:--------|:----------|
|provider |String|Specific provider (product/service - not vendor company); for example, WindowsDefenderATP.|
|providerVersion|String|Version of the provider or subprovider, if it exists, that generated the alert. *Required*|
|subProvider|String|Specific subprovider (under aggregating provider); for example, WindowsDefenderATP.SmartScreen.|
|vendor |String|Name of the alert vendor (for example, Microsoft, Dell, FireEye). *Required*|


## JSON representation

Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.securityVendorInformation"
}-->

```json
{
  "provider": "String",
  "providerVersion": "String",
  "subProvider": "String",
  "vendor": "String"
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "securityVendorInformation resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

