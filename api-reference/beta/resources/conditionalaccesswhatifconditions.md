---
title: "conditionalAccessWhatIfConditions resource type"
description: "**TODO: Add Description**"
author: "**TODO: Provide GitHub Name. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
ms.localizationpriority: medium
ms.subservice: "**TODO: Add MS prod. See [topic-level metadata reference](https://aka.ms/msgo?pagePath=Document-APIs/Guidelines/Metadata)**"
doc_type: resourcePageType
---

# conditionalAccessWhatIfConditions resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

**TODO: Add Description**

## Properties
|Property|Type|Description|
|:---|:---|:---|
|authenticationFlow|[authenticationFlow](../resources/authenticationflow.md)|**TODO: Add Description**|
|clientAppType|conditionalAccessClientApp|**TODO: Add Description**.The possible values are: `all`, `browser`, `mobileAppsAndDesktopClients`, `exchangeActiveSync`, `easSupported`, `other`, `unknownFutureValue`.|
|country|String|**TODO: Add Description**|
|deviceInfo|[deviceInfo](../resources/deviceinfo.md)|**TODO: Add Description**|
|devicePlatform|conditionalAccessDevicePlatform|**TODO: Add Description**.The possible values are: `android`, `iOS`, `windows`, `windowsPhone`, `macOS`, `all`, `unknownFutureValue`, `linux`. Note that you must use the `Prefer: include-unknown-enum-members` request header to get the following value(s) in this [evolvable enum](/graph/best-practices-concept#handling-future-members-in-evolvable-enumerations): `linux`.|
|insiderRiskLevel|insiderRiskLevel|**TODO: Add Description**.The possible values are: `none`, `minor`, `moderate`, `elevated`, `unknownFutureValue`.|
|ipAddress|String|**TODO: Add Description**|
|servicePrincipalRiskLevel|riskLevel|**TODO: Add Description**.The possible values are: `low`, `medium`, `high`, `hidden`, `none`, `unknownFutureValue`.|
|signInRiskLevel|riskLevel|**TODO: Add Description**.The possible values are: `low`, `medium`, `high`, `hidden`, `none`, `unknownFutureValue`.|
|userRiskLevel|riskLevel|**TODO: Add Description**.The possible values are: `low`, `medium`, `high`, `hidden`, `none`, `unknownFutureValue`.|

## Relationships
None.

## JSON representation
The following JSON representation shows the resource type.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.conditionalAccessWhatIfConditions"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.conditionalAccessWhatIfConditions",
  "signInRiskLevel": "String",
  "userRiskLevel": "String",
  "servicePrincipalRiskLevel": "String",
  "country": "String",
  "ipAddress": "String",
  "clientAppType": "String",
  "devicePlatform": "String",
  "deviceInfo": {
    "@odata.type": "microsoft.graph.deviceInfo"
  },
  "insiderRiskLevel": "String",
  "authenticationFlow": {
    "@odata.type": "microsoft.graph.authenticationFlow"
  }
}
```

