---
title: "List microsoftTunnelServers"
description: "List properties and relationships of the microsoftTunnelServer objects."
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# List microsoftTunnelServers

Namespace: microsoft.graph

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

List properties and relationships of the [microsoftTunnelServer](../resources/intune-mstunnel-microsofttunnelserver.md) objects.

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
GET /deviceManagement/microsoftTunnelSites/{microsoftTunnelSiteId}/microsoftTunnelServers
```

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and a collection of [microsoftTunnelServer](../resources/intune-mstunnel-microsofttunnelserver.md) objects in the response body.

## Example

### Request
Here is an example of the request.

<!-- { "blockType": "request" , "name" : "intune_mstunnel_microsofttunnelserver_list_list_microsofttunnelservers" }-->
``` http
GET https://graph.microsoft.com/v1.0/deviceManagement/microsoftTunnelSites/{microsoftTunnelSiteId}/microsoftTunnelServers
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.

<!-- { "blockType": "response" , "@odata.type" : "microsoft.graph.microsoftTunnelServer" }-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 422

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.microsoftTunnelServer",
      "id": "b5cf0aee-0aee-b5cf-ee0a-cfb5ee0acfb5",
      "displayName": "Display Name value",
      "tunnelServerHealthStatus": "healthy",
      "lastCheckinDateTime": "2017-01-01T00:02:46.0431416-08:00",
      "agentImageDigest": "Agent Image Digest value",
      "serverImageDigest": "Server Image Digest value"
    }
  ]
}
```
