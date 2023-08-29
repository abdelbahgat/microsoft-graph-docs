---
title: "Delete sharedWithChannelTeamInfo"
description: "Unshare a channel with a team by deleting the corresponding sharedWithChannelTeamInfo resource."
author: "devjha-ms"
doc_type: "apiPageType"
ms.localizationpriority: high
ms.prod: "microsoft-teams"
---

# Delete sharedWithChannelTeamInfo
Namespace: microsoft.graph

Unshare a [channel](../resources/channel.md) with a [team](../resources/team.md) by deleting the corresponding [sharedWithChannelTeamInfo](../resources/sharedwithchannelteaminfo.md) resource. This operation is allowed only for channels with a **membershipType** value of `shared`.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account) | ChannelMember.ReadWrite.All |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | ChannelMember.ReadWrite.All |


> **Note**: This API supports admin permissions. Global admins and Microsoft Teams service admins can access teams that they are not a member of.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
DELETE /teams/{team-id}/channels/{channel-id}/sharedWithTeams/{shared-with-channel-team-info-id}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `204 No Content` response code.

## Examples

### Request

The following is an example of a request.

<!-- {
  "blockType": "request",
  "name": "delete_sharedwithchannelteaminfo"
}
-->
``` http
DELETE https://graph.microsoft.com/v1.0/teams/ece6f0a1-7ca4-498b-be79-edf6c8fc4d82/channels/19%3A56eb04e133944cf69e603c5dac2d292e%40thread.skype/sharedWithTeams/ece6f0a1-5g39-498b-be79-edf6c8fc4d82
```

### Response

The following is an example of the response.

<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```

## See also

- [Remove member from channel](channel-delete-members.md)
- [Remove member from team](team-delete-members.md)
