---
title: "List deviceAndAppManagementAssignmentFilters"
description: "List properties and relationships of the deviceAndAppManagementAssignmentFilter objects."
author: "dougeby"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# List deviceAndAppManagementAssignmentFilters

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

List properties and relationships of the [deviceAndAppManagementAssignmentFilter](../resources/intune-policyset-deviceandappmanagementassignmentfilter.md) objects.

## Prerequisites
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementConfiguration.Read.All, DeviceManagementConfiguration.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|DeviceManagementConfiguration.Read.All, DeviceManagementConfiguration.ReadWrite.All|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /deviceManagement/assignmentFilters
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and a collection of [deviceAndAppManagementAssignmentFilter](../resources/intune-policyset-deviceandappmanagementassignmentfilter.md) objects in the response body.

## Example

### Request
Here is an example of the request.
``` http
GET https://graph.microsoft.com/beta/deviceManagement/assignmentFilters
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 523

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.deviceAndAppManagementAssignmentFilter",
      "id": "819818db-18db-8198-db18-9881db189881",
      "createdDateTime": "2017-01-01T00:02:43.5775965-08:00",
      "lastModifiedDateTime": "2017-01-01T00:00:35.1329464-08:00",
      "displayName": "Display Name value",
      "description": "Description value",
      "platform": "androidForWork",
      "rule": "Rule value",
      "roleScopeTags": [
        "Role Scope Tags value"
      ]
    }
  ]
}
```




