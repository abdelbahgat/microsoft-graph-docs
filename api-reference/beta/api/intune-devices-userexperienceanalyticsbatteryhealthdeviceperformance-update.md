---
title: "Update userExperienceAnalyticsBatteryHealthDevicePerformance"
description: "Update the properties of a userExperienceAnalyticsBatteryHealthDevicePerformance object."
author: "dougeby"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# Update userExperienceAnalyticsBatteryHealthDevicePerformance

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Update the properties of a [userExperienceAnalyticsBatteryHealthDevicePerformance](../resources/intune-devices-userexperienceanalyticsbatteryhealthdeviceperformance.md) object.

## Prerequisites
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
PATCH /deviceManagement/userExperienceAnalyticsBatteryHealthDevicePerformance/{userExperienceAnalyticsBatteryHealthDevicePerformanceId}
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
In the request body, supply a JSON representation for the [userExperienceAnalyticsBatteryHealthDevicePerformance](../resources/intune-devices-userexperienceanalyticsbatteryhealthdeviceperformance.md) object.

The following table shows the properties that are required when you create the [userExperienceAnalyticsBatteryHealthDevicePerformance](../resources/intune-devices-userexperienceanalyticsbatteryhealthdeviceperformance.md).

|Property|Type|Description|
|:---|:---|:---|
|id|String|The unique identifier of the user experience analytics battery health device performance object.|
|deviceId|String|The unique identifier of the device, Intune DeviceID.|
|deviceName|String|Device friendly name.|
|model|String|The model name of the device.|
|manufacturer|String|The manufacturer name of the device.|
|maxCapacityPercentage|Int32|Ratio of current capacity and design capacity of the battery with the lowest capacity. Unit in percentage and values range from 0-100. Valid values -2147483648 to 2147483647|
|estimatedRuntimeInMinutes|Int32|The estimated runtime of the device when the battery is fully charged. Unit in minutes. Valid values -2147483648 to 2147483647|
|batteryAgeInDays|Int32|Estimated battery age. Unit in days. Valid values -2147483648 to 2147483647|
|deviceBatteryHealthScore|Int32|A weighted average of a device’s maximum capacity score and runtime estimate score. Values range from 0-100. Valid values -2147483648 to 2147483647|
|healthStatus|[userExperienceAnalyticsHealthState](../resources/intune-devices-userexperienceanalyticshealthstate.md)|The overall battery health status of the device. Possible values are: `unknown`, `insufficientData`, `needsAttention`, `meetingGoals`.|



## Response
If successful, this method returns a `200 OK` response code and an updated [userExperienceAnalyticsBatteryHealthDevicePerformance](../resources/intune-devices-userexperienceanalyticsbatteryhealthdeviceperformance.md) object in the response body.

## Example

### Request
Here is an example of the request.
``` http
PATCH https://graph.microsoft.com/beta/deviceManagement/userExperienceAnalyticsBatteryHealthDevicePerformance/{userExperienceAnalyticsBatteryHealthDevicePerformanceId}
Content-type: application/json
Content-length: 400

{
  "@odata.type": "#microsoft.graph.userExperienceAnalyticsBatteryHealthDevicePerformance",
  "deviceId": "Device Id value",
  "deviceName": "Device Name value",
  "model": "Model value",
  "manufacturer": "Manufacturer value",
  "maxCapacityPercentage": 5,
  "estimatedRuntimeInMinutes": 9,
  "batteryAgeInDays": 0,
  "deviceBatteryHealthScore": 8,
  "healthStatus": "insufficientData"
}
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 449

{
  "@odata.type": "#microsoft.graph.userExperienceAnalyticsBatteryHealthDevicePerformance",
  "id": "c8b9e0fd-e0fd-c8b9-fde0-b9c8fde0b9c8",
  "deviceId": "Device Id value",
  "deviceName": "Device Name value",
  "model": "Model value",
  "manufacturer": "Manufacturer value",
  "maxCapacityPercentage": 5,
  "estimatedRuntimeInMinutes": 9,
  "batteryAgeInDays": 0,
  "deviceBatteryHealthScore": 8,
  "healthStatus": "insufficientData"
}
```




