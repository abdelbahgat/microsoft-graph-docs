---
title: "deviceManagementConfigurationSettingApplicability resource type"
description: "Not yet documented"
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: resourcePageType
---

# deviceManagementConfigurationSettingApplicability resource type

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Not yet documented

## Properties
|Property|Type|Description|
|:---|:---|:---|
|description|String|description of the setting|
|platform|[deviceManagementConfigurationPlatforms](../resources/intune-shared-devicemanagementconfigurationplatforms.md)|Platform setting can be applied on. Possible values are: `none`, `android`, `iOS`, `macOS`, `windows10X`, `windows10`, `linux`, `unknownFutureValue`.|
|deviceMode|[deviceManagementConfigurationDeviceMode](../resources/intune-shared-devicemanagementconfigurationdevicemode.md)|Device Mode that setting can be applied on. Possible values are: `none`, `kiosk`.|
|technologies|[deviceManagementConfigurationTechnologies](../resources/intune-shared-devicemanagementconfigurationtechnologies.md)|Which technology channels this setting can be deployed through. Possible values are: `none`, `mdm`, `windows10XManagement`, `configManager`, `appleRemoteManagement`, `microsoftSense`, `exchangeOnline`, `linuxMdm`, `enrollment`, `endpointPrivilegeManagement`, `unknownFutureValue`.|

## Relationships
None

## JSON Representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.deviceManagementConfigurationSettingApplicability"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceManagementConfigurationSettingApplicability",
  "description": "String",
  "platform": "String",
  "deviceMode": "String",
  "technologies": "String"
}
```
