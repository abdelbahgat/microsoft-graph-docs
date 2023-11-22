---
title: "Get educationRubric"
description: "Retrieve the properties and relationships of an educationrubric object."
ms.localizationpriority: medium
author: "Sureshpadimi88"
ms.prod: "education"
doc_type: "apiPageType"
---

# Get educationRubric

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the properties and relationships of an [educationRubric](../resources/educationrubric.md) object. Only teachers and students can perform this operation.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "educationrubric_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/educationrubric-get-permissions.md)]

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /education/me/rubrics/{id}
```

## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization | Bearer {token} |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and the requested [educationRubric](../resources/educationrubric.md) object in the response body.

## Examples

### Request

Here's an example  of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_educationrubric"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/education/me/rubrics/bf040af7-a5ff-4abe-a8c8-1bdc532344c2
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-educationrubric-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-educationrubric-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-educationrubric-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-educationrubric-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-educationrubric-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-educationrubric-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-educationrubric-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-educationrubric-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

Here's an example  of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.educationRubric"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "displayName": "Example Points Rubric",
  "id": "bf040af7-a5ff-4abe-a8c8-1bdc532344c2",
  "description": {
    "content": "This is an example of a rubric with points",
    "contentType": "text"
  },
  "levels": [
    {
      "levelId": "519cd134-c513-40b9-aa71-fdb0d063c084",
      "displayName": "Good",
      "description": {
        "content": "",
        "contentType": "text"
      },
      "grading": {
        "@odata.type": "#microsoft.graph.educationAssignmentPointsGradeType",
        "maxPoints": 2
      }
    },
    {
      "levelId": "db2a0c91-abef-44cb-b8b1-ef1f85ef4a77",
      "displayName": "Poor",
      "description": {
        "content": "",
        "contentType": "text"
      },
      "grading": {
        "@odata.type": "#microsoft.graph.educationAssignmentPointsGradeType",
        "maxPoints": 1
      }
    }
  ],
  "qualities": [
    {
      "qualityId": "bbf3fb4a-a794-4b51-a1ad-c22fb891c5d8",
      "weight": 50.0,
      "description": {
        "content": "Argument",
        "contentType": "text"
      },
      "criteria": [
        {
          "id": "5e637d79-f26b-4ea6-acd7-73824f0c0967",
          "description": {
            "content": "The essay's argument is persuasive.",
            "contentType": "text"
          }
        },
        {
          "id": "ebdcc27f-d1ec-4aa3-9da7-bd8d7842e3d3",
          "description": {
            "content": "The essay's argument does not make sense.",
            "contentType": "text"
          }
        }
      ]
    },
    {
      "qualityId": "ebe97fd7-47f7-4e9a-b31b-221ad731fc5a",
      "weight": 50.0,
      "description": {
        "content": "Spelling and Grammar",
        "contentType": "text"
      },
      "criteria": [
        {
          "id": "5417252a-f810-41eb-9a83-09276a258a08",
          "description": {
            "content": "The essay uses proper spelling and grammar with few or no errors.",
            "contentType": "text"
          }
        },
        {
          "id": "5de220bd-74b9-41a7-85d5-9be7c6cb7933",
          "description": {
            "content": "The essay has numerous errors in spelling and/or grammar.",
            "contentType": "text"
          }
        }
      ]
    }
  ],
  "grading": {
    "@odata.type": "#microsoft.graph.educationAssignmentPointsGradeType",
    "maxPoints": 100
  }
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get educationRubric",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


