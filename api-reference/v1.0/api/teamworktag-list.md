---
title: "List teamworkTags"
description: "Get a list of the teamworkTag objects and their properties."
author: "RamjotSingh"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: apiPageType
---

# List teamworkTags
Namespace: microsoft.graph

Get a list of the [tag](../resources/teamworktag.md) objects and their properties.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from most to least privileged)|
|:---|:---|
|Delegated (work or school account)|TeamworkTag.Read, TeamworkTag.ReadWrite|
|Delegated (personal Microsoft account)|Not supported.|
|Application|TeamworkTag.Read.All, TeamworkTag.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /teams/{team-id}/tags
```

## Optional query parameters
This method supports the `$filter` [OData query parameter](/graph/query-parameters) to help customize the response.

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [teamworkTag](../resources/teamworktag.md) objects in the response body.

## Examples

### Request

The following is an example of a request.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "list_teamworktag",
  "sampleKeys": ["53c53217-fe77-4383-bc5a-ed4937a1aecd"]
}
-->
``` http
GET https://graph.microsoft.com/v1.0/teams/53c53217-fe77-4383-bc5a-ed4937a1aecd/tags
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/list-teamworktag-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/list-teamworktag-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/list-teamworktag-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/list-teamworktag-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/list-teamworktag-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/list-teamworktag-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.teamworkTag",
  "isCollection": true
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.teamworkTag",
      "id": "MjQzMmI1N2ItMGFiZC00M2RiLWFhN2ItMTZlYWRkMTE1ZDM0IyM3ZDg4M2Q4Yi1hMTc5LTRkZDctOTNiMy1hOGQzZGUxYTIxMmUjI3RhY29VSjN2RGk==",
      "teamId": "53c53217-fe77-4383-bc5a-ed4937a1aecd",
      "displayName": "Finance",
      "description": "Finance Team for Mach 8 Project",
      "memberCount": 2,
      "tagType": "standard"
    },
    {
      "@odata.type": "#microsoft.graph.teamworkTag",
      "id": "MjQzMmI1N2ItMGFiZC00M2RiLWFhN2ItMTZlYWRkMTE1ZDM0IyNlYjY1M2Y5Mi04MzczLTRkZTYtYmZlYy01YjRkMjE2YjZhZGUjIzk3ZjYyMzQ0LTU3ZGMtNDA5Yy04OGFkLWM0YWYxNDE1OGZmNQ==",
      "teamId": "53c53217-fe77-4383-bc5a-ed4937a1aecd",
      "displayName": "Legal",
      "description": "Legal experts, ask us your legal questions",
      "memberCount": 4,
      "tagType": "standard"
    }
  ]
}
```

