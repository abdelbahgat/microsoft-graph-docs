---
title: "deviceManagementConfigurationSimpleSettingInstance resource type"
description: "Simple setting instance"
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: resourcePageType
---

# deviceManagementConfigurationSimpleSettingInstance resource type

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Simple setting instance


Inherits from [deviceManagementConfigurationSettingInstance](../resources/intune-shared-devicemanagementconfigurationsettinginstance.md)

## Properties
|Property|Type|Description|
|:---|:---|:---|
|settingDefinitionId|String|Setting Definition Id Inherited from [deviceManagementConfigurationSettingInstance](../resources/intune-shared-devicemanagementconfigurationsettinginstance.md)|
|settingInstanceTemplateReference|[deviceManagementConfigurationSettingInstanceTemplateReference](../resources/intune-shared-devicemanagementconfigurationsettinginstancetemplatereference.md)|Setting Instance Template Reference Inherited from [deviceManagementConfigurationSettingInstance](../resources/intune-shared-devicemanagementconfigurationsettinginstance.md)|
|simpleSettingValue|[deviceManagementConfigurationSimpleSettingValue](../resources/intune-mam-devicemanagementconfigurationsimplesettingvalue.md)|Simple setting instance value|

## Relationships
None

## JSON Representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.deviceManagementConfigurationSimpleSettingInstance"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceManagementConfigurationSimpleSettingInstance",
  "settingDefinitionId": "String",
  "settingInstanceTemplateReference": {
    "@odata.type": "microsoft.graph.deviceManagementConfigurationSettingInstanceTemplateReference",
    "settingInstanceTemplateId": "String"
  },
  "simpleSettingValue": {
    "@odata.type": "microsoft.graph.deviceManagementConfigurationSimpleSettingValue"
  }
}
```
