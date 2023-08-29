---
title: "reports: getGroupArchivedPrintJobs"
description: Get a list of archived print jobs for a particular group.
author: nilakhan
ms.localizationpriority: medium
ms.prod: cloud-printing
doc_type: apiPageType
---

# reportRoot: getGroupArchivedPrintJobs
Namespace: microsoft.graph

Get a list of archived print jobs for a particular group.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

In addition to the following permissions, the user's tenant must have an active Universal Print subscription.

|Permission type | Permissions (from least to most privileged) |
|:---------------|:--------------------------------------------|
|Delegated (work or school account)| Reports.Read.All |
|Delegated (personal Microsoft account)|Not Supported.|
|Application|Not Supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /reports/getGroupArchivedPrintJobs
```

## Function parameters
In the request URL, provide the following function parameters with values:

| Parameter     | Type                 | Required? | Description                                                          |
|---------------|----------------------|-----------|----------------------------------------------------------------------|
| `groupId`     | `Edm.String`         | Yes       | The ID of the group to return data for.                              |
| `startDateTime` | `Edm.DateTimeOffset` | No        | The start date (inclusive) for the time period to include data from.|
| `endDateTime`   | `Edm.DateTimeOffset` | No        | The end date (inclusive) for the time period to include data from.|

>**Note:** If a value is not required, pass the parameter with null value.
## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this function returns a `200 OK` response code and a [archivedPrintJob](../resources/archivedprintjob.md) collection in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "reports_getgrouparchivedprintjobs"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/reports/getGroupArchivedPrintJobs(groupId='{id}',startDateTime=<timestamp>,endDateTime=<timestamp>)
```

### Response
**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.archivedPrintJob)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "id": "016b5565-3bbf-4067-b9ff-4d68167eb1a6",
      "printerId": "fe6ff85a-f0d3-4c4f-aec6-b9d5154356a1",
      "createdBy": {},
      "processingState": "completed"
    }
  ]
}
```

