---
title: "List microsoftTunnelSites"
description: "List properties and relationships of the microsoftTunnelSite objects."
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# List microsoftTunnelSites

Namespace: microsoft.graph

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

List properties and relationships of the [microsoftTunnelSite](../resources/intune-mstunnel-microsofttunnelsite.md) objects.

## Permissions
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
GET /deviceManagement/microsoftTunnelSites
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and a collection of [microsoftTunnelSite](../resources/intune-mstunnel-microsofttunnelsite.md) objects in the response body.

## Example

### Request
Here is an example of the request.

<!-- { "blockType": "request" , "name" : "intune_mstunnel_microsofttunnelsite_list_list_microsofttunnelsites" }-->
``` http
GET https://graph.microsoft.com/v1.0/deviceManagement/microsoftTunnelSites
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

<!-- { "blockType": "response" , "@odata.type" : "microsoft.graph.microsoftTunnelSite" }-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 662

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.microsoftTunnelSite",
      "id": "b2f7dc3e-dc3e-b2f7-3edc-f7b23edcf7b2",
      "displayName": "Display Name value",
      "description": "Description value",
      "publicAddress": "Public Address value",
      "upgradeWindowUtcOffsetInMinutes": 15,
      "upgradeWindowStartTime": "12:01:27.3030000",
      "upgradeWindowEndTime": "11:57:17.9830000",
      "upgradeAutomatically": true,
      "upgradeAvailable": true,
      "internalNetworkProbeUrl": "https://example.com/internalNetworkProbeUrl/",
      "roleScopeTagIds": [
        "Role Scope Tag Ids value"
      ]
    }
  ]
}
```
