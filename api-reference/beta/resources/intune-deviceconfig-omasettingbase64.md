---
title: "omaSettingBase64 resource type"
description: "OMA Settings Base64 definition."
author: "dougeby"
localization_priority: Normal
ms.prod: "intune"
doc_type: resourcePageType
---

# omaSettingBase64 resource type

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

OMA Settings Base64 definition.


Inherits from [omaSetting](../resources/intune-deviceconfig-omasetting.md)

## Properties
|Property|Type|Description|
|:---|:---|:---|
|displayName|String|Display Name. Inherited from [omaSetting](../resources/intune-deviceconfig-omasetting.md)|
|description|String|Description. Inherited from [omaSetting](../resources/intune-deviceconfig-omasetting.md)|
|omaUri|String|OMA. Inherited from [omaSetting](../resources/intune-deviceconfig-omasetting.md)|
|secretReferenceValueId|String|ReferenceId for looking up secret for decryption. This property is read-only. Inherited from [omaSetting](../resources/intune-deviceconfig-omasetting.md)|
|isEncrypted|Boolean|Indicates whether the value field is encrypted. This property is read-only. Inherited from [omaSetting](../resources/intune-deviceconfig-omasetting.md)|
|fileName|String|File name associated with the Value property (*.cer | *.crt | *.p7b | *.bin).|
|value|String|Value. (Base64 encoded string)|

## Relationships
None

## JSON Representation
Here is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.omaSettingBase64"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.omaSettingBase64",
  "displayName": "String",
  "description": "String",
  "omaUri": "String",
  "secretReferenceValueId": "String",
  "isEncrypted": true,
  "fileName": "String",
  "value": "String"
}
```




