---
title: "deviceManagementConfigurationSettingDefinition resource type"
description: "Not yet documented"
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: resourcePageType
---

# deviceManagementConfigurationSettingDefinition resource type

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Not yet documented

## Methods
|Method|Return Type|Description|
|:---|:---|:---|
|[List deviceManagementConfigurationSettingDefinitions](../api/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition-list.md)|[deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md) collection|List properties and relationships of the [deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md) objects.|
|[Get deviceManagementConfigurationSettingDefinition](../api/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition-get.md)|[deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md)|Read properties and relationships of the [deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md) object.|
|[Create deviceManagementConfigurationSettingDefinition](../api/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition-create.md)|[deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md)|Create a new [deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md) object.|
|[Delete deviceManagementConfigurationSettingDefinition](../api/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition-delete.md)|None|Deletes a [deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md).|
|[Update deviceManagementConfigurationSettingDefinition](../api/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition-update.md)|[deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md)|Update the properties of a [deviceManagementConfigurationSettingDefinition](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingdefinition.md) object.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|applicability|[deviceManagementConfigurationSettingApplicability](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingapplicability.md)|Details which device setting is applicable on. Supports: $filters.|
|accessTypes|[deviceManagementConfigurationSettingAccessTypes](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingaccesstypes.md)|Read/write access mode of the setting. Possible values are: `none`, `add`, `copy`, `delete`, `get`, `replace`, `execute`.|
|keywords|String collection|Tokens which to search settings on|
|infoUrls|String collection|List of links more info for the setting can be found at.|
|occurrence|[deviceManagementConfigurationSettingOccurrence](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingoccurrence.md)|Indicates whether the setting is required or not|
|baseUri|String|Base CSP Path|
|offsetUri|String|Offset CSP Path from Base|
|rootDefinitionId|String|Root setting definition id if the setting is a child setting.|
|categoryId|String|Specify category in which the setting is under. Support $filters.|
|settingUsage|[deviceManagementConfigurationSettingUsage](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingusage.md)|Indicate setting type for the setting. Possible values are: configuration, compliance, reusableSetting. Each setting usage has separate API end-point to call. Possible values are: `none`, `configuration`, `compliance`, `unknownFutureValue`.|
|uxBehavior|[deviceManagementConfigurationControlType](../resources/intune-deviceconfigv2-devicemanagementconfigurationcontroltype.md)|Setting control type representation in the UX. Possible values are: default, dropdown, smallTextBox, largeTextBox, toggle, multiheaderGrid, contextPane. Possible values are: `default`, `dropdown`, `smallTextBox`, `largeTextBox`, `toggle`, `multiheaderGrid`, `contextPane`, `unknownFutureValue`.|
|visibility|[deviceManagementConfigurationSettingVisibility](../resources/intune-deviceconfigv2-devicemanagementconfigurationsettingvisibility.md)|Setting visibility scope to UX. Possible values are: none, settingsCatalog, template. Possible values are: `none`, `settingsCatalog`, `template`, `unknownFutureValue`.|
|referredSettingInformationList|[deviceManagementConfigurationReferredSettingInformation](../resources/intune-deviceconfigv2-devicemanagementconfigurationreferredsettinginformation.md) collection|List of referred setting information.|
|id|String|Identifier for item|
|description|String|Description of the setting.|
|helpText|String|Help text of the setting. Give more details of the setting.|
|name|String|Name of the item|
|displayName|String|Name of the setting. For example: Allow Toast.|
|version|String|Item Version|

## Relationships
None

## JSON Representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.deviceManagementConfigurationSettingDefinition"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceManagementConfigurationSettingDefinition",
  "applicability": {
    "@odata.type": "microsoft.graph.deviceManagementConfigurationSettingApplicability",
    "description": "String",
    "platform": "String",
    "deviceMode": "String",
    "technologies": "String"
  },
  "accessTypes": "String",
  "keywords": [
    "String"
  ],
  "infoUrls": [
    "String"
  ],
  "occurrence": {
    "@odata.type": "microsoft.graph.deviceManagementConfigurationSettingOccurrence",
    "minDeviceOccurrence": 1024,
    "maxDeviceOccurrence": 1024
  },
  "baseUri": "String",
  "offsetUri": "String",
  "rootDefinitionId": "String",
  "categoryId": "String",
  "settingUsage": "String",
  "uxBehavior": "String",
  "visibility": "String",
  "referredSettingInformationList": [
    {
      "@odata.type": "microsoft.graph.deviceManagementConfigurationReferredSettingInformation",
      "settingDefinitionId": "String"
    }
  ],
  "id": "String (identifier)",
  "description": "String",
  "helpText": "String",
  "name": "String",
  "displayName": "String",
  "version": "String"
}
```
