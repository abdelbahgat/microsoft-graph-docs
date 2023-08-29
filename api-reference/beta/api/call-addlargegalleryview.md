---
title: "call: addLargeGalleryView"
description: "Add the large gallery view to a call."
author: "navali-msft"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: apiPageType
---

# call: addLargeGalleryView

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Add the large gallery view to a call.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type | Permissions (from least to most privileged) |
| :-------------- | :------------------------------------------ |
| Delegated (work or school account)     | Not supported.       |
| Delegated (personal Microsoft account) | Not supported.       |
| Application     | Calls.JoinGroupCallAsGuest.All, Calls.JoinGroupCall.All, Calls.InitiateGroupCall.All                       |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /app/calls/{id}/addLargeGalleryView
POST /communications/calls/{id}/addLargeGalleryView
```

> **Note:** The `/app` path is deprecated. Going forward, use the `/communications` path.

## Request headers
| Name          | Description                |
|:--------------|:---------------------------|
| Authorization | Bearer {token}. Required.  |
| Content-Type  | application/json. Required.|

## Request body
In the request body, provide a JSON object with the following parameter.

| Parameter      | Type    | Description |
|:---------------|:--------|:------------|
| clientContext  | String  | Unique client context string that can have a maximum of 256 characters. |

## Response
If successful, this method returns a `202 Accepted` response code and an [addLargeGalleryViewOperation](../resources/addlargegalleryviewoperation.md) object in the response body.

## Example

### Request

The following example shows how to add the large gallery view to a call.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "addLargeGalleryView-1"
}-->
```http
POST https://graph.microsoft.com/beta/communications/calls/57dab8b1-894c-409a-b240-bd8beae78896/addLargeGalleryView
Content-Type: application/json
Content-Length: 46

{
  "clientContext": "785f4929-92ca-497b-863f-c778c77c9758"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/addlargegalleryview-1-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/addlargegalleryview-1-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/addlargegalleryview-1-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/addlargegalleryview-1-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/addlargegalleryview-1-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/addlargegalleryview-1-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "name": "addLargeGalleryView-1",
  "truncated": true,
  "@odata.type": "microsoft.graph.addLargeGalleryViewOperation"
} -->
```http
HTTP/1.1 202 ACCEPTED
Location: https://graph.microsoft.com/beta/communications/calls/57dab8b1-894c-409a-b240-bd8beae78896/operations/e33176d4-836a-4fd7-b95a-d11bda52811d

{
  "@odata.type": "#microsoft.graph.addLargeGalleryViewOperation",
  "clientContext": "785f4929-92ca-497b-863f-c778c77c9758",
  "id": "e33176d4-836a-4fd7-b95a-d11bda52811d",
  "resultInfo": null,
  "status": "running"
}
```

### Notification - operation completed

```http
POST https://bot.contoso.com/api/calls
Content-Type: application/json
```

<!-- {
  "blockType": "example",
  "@odata.type": "microsoft.graph.commsNotifications"
}-->
```json
{
  "@odata.type": "#microsoft.graph.commsNotifications",
  "value": [
    {
      "@odata.type": "#microsoft.graph.commsNotification",
      "changeType": "deleted",
      "resourceUrl": "/communications/calls/57dab8b1-894c-409a-b240-bd8beae78896/operations/e33176d4-836a-4fd7-b95a-d11bda52811d",
      "resourceData": {
        "@odata.type": "#microsoft.graph.addLargeGalleryViewOperation",
        "@odata.id": "/communications/calls/57dab8b1-894c-409a-b240-bd8beae78896/operations/e33176d4-836a-4fd7-b95a-d11bda52811d",
        "clientContext": "785f4929-92ca-497b-863f-c778c77c9758",
        "status": "completed"
      }
    }
  ]
}
```

## See also

- [Learn how to identify the large gallery view participant in a call](/graph/cloud-communications-identifylargegalleryview)

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "call: addLargeGalleryView",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->
