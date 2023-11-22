---
title: "reports: destinationReport"
description: "Retrieve a report containing information about all outgoing network connections within a specified time frame."
author: Moti-ba
ms.localizationpriority: medium
ms.prod: global-secure-access
doc_type: apiPageType
---

# reports: destinationReport
Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve a report containing information about all outgoing network connections within a specified time frame.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|NetworkAccessPolicy.Read.All,NetworkAccessPolicy.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

[!INCLUDE [rbac-global-secure-access-apis-read](../includes/rbac-for-apis/rbac-global-secure-access-apis-read.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /networkAccessRoot/reports/destinationReport(startDateTime={startDateTime}, endDateTime={endDateTime})
```

## Function parameters
In the request URL, provide the following query parameters with values.
The following table shows the parameters that can be used with this function.

|Parameter|Type|Description|
|:---|:---|:---|
|startDateTime|DateTimeOffset|The time and date of the beginning of the report period.|
|endDateTime|DateTimeOffset|The time and date of the end of the report period.|


## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Don't supply a request body for this method.

## Response

If successful, this function returns a `200 OK` response code and a [microsoft.graph.networkaccess.destination](../resources/networkaccess-destination.md) collection in the response body.

## Examples

### Request
The following example shows a request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "reportsthis.destinationreport"
}
-->
``` http
GET https://graph.microsoft.com/beta/networkaccess/reports/destinationReport(startDateTime=2023-08-20T12:12:59.076Z, endDateTime=2023-08-21T12:12:59.076Z) 
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/reportsthisdestinationreport-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/reportsthisdestinationreport-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### Response
The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.networkaccess.destination)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context":"https://graph.microsoft.com/beta/$metadata#Collection(microsoft.graph.networkaccess.destination)",
  "value":[
     {
        "fqdn":"login.microsoftonline.com",
        "ip":"6.6.0.1",
        "port":443,
        "networkingProtocol":"TCP",
        "trafficProfile":"microsoft365",
        "lastAccessDateTime":"2023-08-09T13:20:04Z",
        "trafficType":"microsoft365"
     },
     {
        "ip":"130.20.20.20",
        "port":443,
        "networkingProtocol":"TCP",
        "trafficProfile":"private",
        "lastAccessDateTime":"2023-08-09T13:20:04Z",
        "trafficType":"private"
     }
  ]
}
```

