---
title: "Get unifiedStorageQuota"
description: "Read the properties and relationships of a unifiedStorageQuota object."
author: "BarryShehadeh"
ms.localizationpriority: medium
ms.prod: files
doc_type: apiPageType
---

# Get unifiedStorageQuota
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Read the properties and relationships of a [unifiedStorageQuota](../resources/unifiedstoragequota.md) object.

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "unifiedstoragequota_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/unifiedstoragequota-get-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /me/settings/storage/quota
GET /users/{user-id}/settings/storage/quota
```

## Optional query parameters
This method supports some of the OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a [unifiedStorageQuota](../resources/unifiedstoragequota.md) object in the response body.

## Examples

### Example 1: Get the unified quota information for the current user
#### Request
Here's an example  of a request.
<!-- {
  "blockType": "request",
  "name": "get_unifiedstoragequota"
}
-->
``` http
GET https://graph.microsoft.com/beta/me/settings/storage/quota
```


#### Response
Here's an example  of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.unifiedStorageQuota"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.unifiedStorageQuota",
    "manageWebUrl": "String",
    "remaining": 1066671526110,
    "state": "normal",
    "total": 1169304846336,
    "used": 102633320226
  }
}
```

### Example 2: Get the unified quota information for the current user
#### Request
Here's an example  of a request.
<!-- {
  "blockType": "request",
  "name": "get_unifiedstoragequotabyuserid",
  "sampleKeys": ["1234BBS1121YY95"]
}
-->
``` http
GET https://graph.microsoft.com/beta/users/1234BBS1121YY95/settings/storage/quota
```


#### Response
Here's an example  of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.unifiedStorageQuota"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.unifiedStorageQuota",
    "manageWebUrl": "String",
    "remaining": 1066671526110,
    "state": "normal",
    "total": 1169304846336,
    "used": 102633320226
  }
}
```

### Example 3: Get the unified quota information, along with the service breakdowns, for the current user
#### Request
Here's an example  of a request.
<!-- {
  "blockType": "request",
  "name": "get_unifiedstoragequotaandservices"
}
-->
``` http
GET https://graph.microsoft.com/beta/me/settings/storage/quota?$expand=services
```


#### Response
Here's an example  of the response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.unifiedStorageQuota"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": {
    "@odata.type": "#microsoft.graph.unifiedStorageQuota",
    "manageWebUrl": "String",
    "remaining": 1066671526110,
    "state": "normal",
    "total": 1169304846336,
    "used": 102633320226,
    "services": [
        {
            "displayName": "OneDrive",
            "id": "OneDrive",
            "used": 102633320226
        },
        {
            "displayName": "Outlook (Attachments)",
            "id": "Outlook",
            "used": 123
        }
    ]
  }
}
```
