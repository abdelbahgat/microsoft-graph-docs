---
title: "Get sharedWithChannelTeamInfo"
description: "Get a team that has been shared with a specified channel."
author: "devjha-ms"
doc_type: "apiPageType"
ms.localizationpriority: high
ms.prod: "microsoft-teams"
---

# Get sharedWithChannelTeamInfo
Namespace: microsoft.graph

Get a [team](../resources/sharedwithchannelteaminfo.md) that has been shared with a specified [channel](../resources/channel.md). This operation is allowed only for channels with a **membershipType** value of `shared`.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|ChannelMember.Read.All, ChannelMember.ReadWrite.All |
|Delegated (personal Microsoft account)|Not supported.|
|Application|ChannelMember.Read.All, ChannelMember.ReadWrite.All |

> **Note**: This API supports admin permissions. Global admins and Microsoft Teams service admins can access teams that they are not a member of.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /teams/{team-id}/channels/{channel-id}/sharedWithTeams/{shared-with-channel-team-info-id}
```

## Optional query parameters
This method does not support the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [sharedWithChannelTeamInfo](../resources/sharedwithchannelteaminfo.md) object in the response body.

## Examples

### Request
The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "get_sharedwithchannelteaminfo"
}
-->
``` http
GET https://graph.microsoft.com/v1.0/teams/893075dd-2487-5634-925f-022c42e20265/channels/19:561fbdbbfca848a484f0a6f00ce9dbbd@thread.tacv2/sharedWithTeams/893075dd-2487-5634-925f-022c42e20265
```


### Response
The following is an example of the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.sharedWithChannelTeamInfo"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.sharedWithChannelTeamInfo",
    "id": "2173de69-de69-2173-69de-732169de7321",
    "tenantId": "b3246f44-b4gb-4627-96c6-25b18fa2c910",
    "displayName": "Team contoso",
    "isHostTeam": true
  }
}
```

