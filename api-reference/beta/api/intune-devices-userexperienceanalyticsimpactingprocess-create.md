---
title: "Create userExperienceAnalyticsImpactingProcess"
description: "Create a new userExperienceAnalyticsImpactingProcess object."
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# Create userExperienceAnalyticsImpactingProcess

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Create a new [userExperienceAnalyticsImpactingProcess](../resources/intune-devices-userexperienceanalyticsimpactingprocess.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementConfiguration.ReadWrite.All, DeviceManagementManagedDevices.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|DeviceManagementConfiguration.ReadWrite.All, DeviceManagementManagedDevices.ReadWrite.All|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /deviceManagement/userExperienceAnalyticsImpactingProcess
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
In the request body, supply a JSON representation for the userExperienceAnalyticsImpactingProcess object.

The following table shows the properties that are required when you create the userExperienceAnalyticsImpactingProcess.

|Property|Type|Description|
|:---|:---|:---|
|id|String|The unique identifier of the user experience analytics top impacting process entity.|
|deviceId|String|The unique identifier of the impacted device.|
|category|String|The category of impacting process.|
|processName|String|The process name.|
|description|String|The description of process.|
|publisher|String|The publisher of the process.|
|impactValue|Double|The impact value of the process. Valid values 0 to 1.79769313486232E+308|



## Response
If successful, this method returns a `201 Created` response code and a [userExperienceAnalyticsImpactingProcess](../resources/intune-devices-userexperienceanalyticsimpactingprocess.md) object in the response body.

## Example

### Request
Here is an example of the request.
``` http
POST https://graph.microsoft.com/beta/deviceManagement/userExperienceAnalyticsImpactingProcess
Content-type: application/json
Content-length: 300

{
  "@odata.type": "#microsoft.graph.userExperienceAnalyticsImpactingProcess",
  "deviceId": "Device Id value",
  "category": "Category value",
  "processName": "Process Name value",
  "description": "Description value",
  "publisher": "Publisher value",
  "impactValue": 3.6666666666666665
}
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 201 Created
Content-Type: application/json
Content-Length: 349

{
  "@odata.type": "#microsoft.graph.userExperienceAnalyticsImpactingProcess",
  "id": "faefd665-d665-faef-65d6-effa65d6effa",
  "deviceId": "Device Id value",
  "category": "Category value",
  "processName": "Process Name value",
  "description": "Description value",
  "publisher": "Publisher value",
  "impactValue": 3.6666666666666665
}
```
