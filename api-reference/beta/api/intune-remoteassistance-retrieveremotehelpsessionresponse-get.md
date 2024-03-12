---
title: "Get retrieveRemoteHelpSessionResponse"
description: "Read properties and relationships of the retrieveRemoteHelpSessionResponse object."
author: "jaiprakashmb"
localization_priority: Normal
ms.prod: "intune"
doc_type: apiPageType
---

# Get retrieveRemoteHelpSessionResponse

Namespace: microsoft.graph

> **Important:** Microsoft Graph APIs under the /beta version are subject to change; production use is not supported.

> **Note:** The Microsoft Graph API for Intune requires an [active Intune license](https://go.microsoft.com/fwlink/?linkid=839381) for the tenant.

Read properties and relationships of the [retrieveRemoteHelpSessionResponse](../resources/intune-remoteassistance-retrieveremotehelpsessionresponse.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|DeviceManagementServiceConfig.Read.All, DeviceManagementServiceConfig.ReadWrite.All, DeviceManagementConfiguration.Read.All, DeviceManagementConfiguration.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|DeviceManagementServiceConfig.Read.All, DeviceManagementServiceConfig.ReadWrite.All, DeviceManagementConfiguration.Read.All, DeviceManagementConfiguration.ReadWrite.All|

## HTTP Request
<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /RemoteHelpSessionRetrieveResponse/{RemoteHelpSessionRetrieveResponseId}
```

## Optional query parameters
This method supports the [OData Query Parameters](/graph/query-parameters) to help customize the response.

## Request headers
|Header|Value|
|:---|:---|
|Authorization|Bearer &lt;token&gt; Required.|
|Accept|application/json|

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and [retrieveRemoteHelpSessionResponse](../resources/intune-remoteassistance-retrieveremotehelpsessionresponse.md) object in the response body.

## Example

### Request
Here is an example of the request.
``` http
GET https://graph.microsoft.com/beta/RemoteHelpSessionRetrieveResponse/{RemoteHelpSessionRetrieveResponseId}
```

### Response
Here is an example of the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
``` http
HTTP/1.1 200 OK
Content-Type: application/json
Content-Length: 602

{
  "value": {
    "@odata.type": "#microsoft.graph.retrieveRemoteHelpSessionResponse",
    "sessionKey": "Session Key value",
    "acsHelperUserToken": "Acs Helper User Token value",
    "acsHelperUserId": "Acs Helper User Id value",
    "acsSharerUserId": "Acs Sharer User Id value",
    "acsGroupId": "Acs Group Id value",
    "sessionType": "takeFullControl",
    "deviceName": "Device Name value",
    "pubSubGroupId": "Pub Sub Group Id value",
    "pubSubHelperAccessUri": "Pub Sub Helper Access Uri value",
    "sessionExpirationDateTime": "2016-12-31T23:59:57.5564522-08:00"
  }
}
```
