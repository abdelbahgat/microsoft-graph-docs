---
title: "userExperienceAnalyticsSummarizedDeviceScopes function"
description: "Intune Devices Devicemanagement Userexperienceanalyticssummarizeddevicescopes Api ."
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# userExperienceAnalyticsSummarizedDeviceScopes function

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.



## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementConfiguration.Read.All, DeviceManagementManagedDevices.Read.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|DeviceManagementConfiguration.Read.All, DeviceManagementManagedDevices.Read.All|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /deviceManagement/userExperienceAnalyticsSummarizedDeviceScopes
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
Do not supply a request body for this method.

## Response
If successful, this function returns a `200 OK` response code and a [userExperienceAnalyticsDeviceScopeSummary](../resources/intune-devices-userexperienceanalyticsdevicescopesummary.md) in the response body.

## Example

### Request
Here is an example of the request.
``` http
GET https://graph.microsoft.com/beta/deviceManagement/userExperienceAnalyticsSummarizedDeviceScopes
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 351

{
  "value": {
    "@odata.type": "microsoft.graph.userExperienceAnalyticsDeviceScopeSummary",
    "totalDeviceScopes": 1,
    "totalDeviceScopesEnabled": 8,
    "completedDeviceScopeIds": [
      "Completed Device Scope Ids value"
    ],
    "insufficientDataDeviceScopeIds": [
      "Insufficient Data Device Scope Ids value"
    ]
  }
}
```
