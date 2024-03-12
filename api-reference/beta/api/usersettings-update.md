---
title: "Update settings"
description: "Update the properties of the settings object. "
author: "yyuank"
ms.localizationpriority: medium
ms.prod: "users"
doc_type: apiPageType
---

# Update settings

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of the [userSettings](../resources/usersettings.md) object. 
Users in the same organization can have different settings based on their preference or on the organization policies. 
To get the user current settings, see [current user settings](usersettings-get.md). 


### Batch request

It's also possible to opt-out multiple users from Delve through a batch request.
To learn more, see [JSON batching](/graph/json-batching).

>**Important**: Only members of the [organization management](https://support.office.com/article/permissions-in-the-office-365-security-compliance-center-d10608af-7934-490a-818e-e68f17d0e9c1?ui=en-US&rs=en-US&ad=US) role group can update multiple users. 



## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | User.ReadWrite, User.ReadWrite.All   |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | User.ReadWrite.All |

## HTTP request

```http
PATCH /me/settings
```

Request with a 'user id' or 'userPrincipalName' is only accessible by the user or by a user with the User.ReadWrite.All permissions. To learn more, see [Permissions](/graph/permissions-reference). 

```http
PATCH /users/{id | userPrincipalName}/settings/
```

## Request headers

| Header       | Value|
|:-----------|:------|
| Authorization  | Bearer {token}. Required.  |
| Content-Type  | application/json  |

## Request body

In the request body, supply the values for relevant fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance you shouldn't include existing values that haven't changed.

| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|contributionToContentDiscoveryDisabled|Boolean|Set to true to disable access to documents in Office Delve for the user. This setting reflects the control state in [Office Delve](https://support.office.com/article/are-my-documents-safe-in-office-delve-f5f409a2-37ed-4452-8f61-681e5e1836f3?ui=en-US&rs=en-US&ad=US#bkmk_optout).|

## Example 

##### Request

Here is an example request on how to opt-out a user from Delve and disable his contribution on content relevancy for the whole organization.

```http
PATCH https://graph.microsoft.com/beta/me/settings
Content-type: application/json

{
  "contributionToContentDiscoveryDisabled": true
}
```

##### Response

Here is an example of the response. Note: The response object shown here might be shortened for readability.

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "contributionToContentDiscoveryAsOrganizationDisabled": false,
  "contributionToContentDiscoveryDisabled": true
}
```



