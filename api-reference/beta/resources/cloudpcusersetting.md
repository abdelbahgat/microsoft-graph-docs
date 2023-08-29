---
title: "cloudPcUserSetting resource type"
description: "Represents a Cloud PC user setting"
author: "AshleyYangSZ"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: resourcePageType
---

# cloudPcUserSetting resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a Cloud PC user setting.

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[List cloudPcUserSettings](../api/virtualendpoint-list-usersettings.md)|[cloudPcUserSetting](../resources/cloudpcusersetting.md) collection|Get a list of the [cloudPcUserSetting](../resources/cloudpcusersetting.md) objects and their properties.|
|[Get cloudPcUserSetting](../api/cloudpcusersetting-get.md)|[cloudPcUserSetting](../resources/cloudpcusersetting.md)|Read the properties and relationships of a [cloudPcUserSetting](../resources/cloudpcusersetting.md) object.|
|[Create cloudPcUserSetting](../api/virtualendpoint-post-usersettings.md)|[cloudPcUserSetting](../resources/cloudpcusersetting.md)|Create a new [cloudPcUserSetting](../resources/cloudpcusersetting.md) object.|
|[Update cloudPcUserSetting](../api/cloudpcusersetting-update.md)|[cloudPcUserSetting](../resources/cloudpcusersetting.md)|Update the properties of a [cloudPcUserSetting](../resources/cloudpcusersetting.md) object.|
|[Delete cloudPcUserSetting](../api/cloudpcusersetting-delete.md)|None|Deletes a [cloudPcUserSetting](../resources/cloudpcusersetting.md) object.|
|[Assign](../api/cloudpcusersetting-assign.md)|None|Assign a [cloudPcUserSetting](../resources/cloudpcusersetting.md) to user groups.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|id|String|Unique identifier for the Cloud PC user setting. Read-only.|
|displayName|String|The setting name displayed in the user interface. |
|localAdminEnabled|Boolean|Indicates whether the local admin option is enabled. Default value is `false`. To enable the local admin option, change the setting to `true`. If the local admin option is enabled, the end user can be an admin of the Cloud PC device. |
|selfServiceEnabled|Boolean|Indicates whether the self-service option is enabled. Default value is `false`. To enable the self-service option, change the setting to `true`. If the self-service option is enabled, the end user is allowed to perform some self-service operations, such as upgrading the Cloud PC through the end user portal.|
|restorePointSetting|[cloudPcRestorePointSetting](../resources/cloudpcrestorepointsetting.md)|Defines how frequently a restore point is created that is, a snapshot is taken) for users' provisioned Cloud PCs (default is 12 hours), and whether the user is allowed to restore their own Cloud PCs to a backup made at a specific point in time.|
|lastModifiedDateTime|DateTimeOffset|The last date and time the setting was modified. The Timestamp type represents the date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 looks like this: '2014-01-01T00:00:00Z'. |
|createdDateTime|DateTimeOffset|The date and time the setting was created. The Timestamp type represents the date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 looks like this: '2014-01-01T00:00:00Z'. |

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|assignments|[cloudPcUserSettingAssignment](../resources/cloudpcusersettingassignment.md) collection|Represents the set of Microsoft 365 groups and security groups in Azure AD that have cloudPCUserSetting assigned. Returned only on `$expand`. For an example, see [Get cloudPcUserSettingample](../api/cloudpcusersetting-get.md).|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.cloudPcUserSetting",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.cloudPcUserSetting",
  "id": "String (identifier)",
  "displayName": "String",
  "selfServiceEnabled": "Boolean",
  "localAdminEnabled": "Boolean",
  "restorePointSetting": {
    "@odata.type": "microsoft.graph.cloudPcRestorePointSetting"
  },
  "lastModifiedDateTime": "String (timestamp)",
  "createdDateTime": "String (timestamp)"
}
```
