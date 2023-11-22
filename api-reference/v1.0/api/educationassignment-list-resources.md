---
title: "List assignment resources"
description: "Get all the resources associated with an assignment."
author: "Sureshpadimi88"
ms.localizationpriority: medium
ms.prod: "education"
doc_type: apiPageType
---

# List assignment resources

Namespace: microsoft.graph

Get all the [educationAssignmentResource](../resources/educationassignmentresource.md) objects associated with an [assignment](../resources/educationassignment.md). Only teachers, students, and applications with application permissions can perform this operation.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "educationassignment_list_resources" } -->
[!INCLUDE [permissions-table](../includes/permissions/educationassignment-list-resources-permissions.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /education/classes/{id}/assignments/{id}/resources
```

## Optional query parameters

This method supports the `$top`, `$filter`, `$orderby`, and `$select` OData query parameters to help customize the response.
For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |

## Request body
Don't supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and a collection of [educationAssignmentResource](../resources/educationassignmentresource.md) objects in the response body.

## Example
### Request
The following example shows a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "sampleKeys": ["f4a941ff-9da6-4707-ba5b-0eae93cad0b4","9018ae7a-9953-4796-a152-4c54e0910922"],
  "name": "get_resources_1"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/education/classes/f4a941ff-9da6-4707-ba5b-0eae93cad0b4/assignments/9018ae7a-9953-4796-a152-4c54e0910922/resources
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-resources-1-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-resources-1-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-resources-1-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-resources-1-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-resources-1-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-resources-1-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-resources-1-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-resources-1-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.educationAssignmentResource",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "value": [
        {
            "distributeForStudentWork": false,
            "id": "eec7f642-9d9a-406f-bbae-4b3b2c12e273",
            "resource": {
                "@odata.type": "#microsoft.graph.educationFileResource",
                "displayName": "First file uploaded as Education resource by t-cristobalb",
                "createdDateTime": "2021-07-16T23:41:53.9378423Z",
                "lastModifiedDateTime": "2021-07-16T23:41:53.9378423Z",
                "fileUrl": "https://graph.microsoft.com/v1.0/drives/b!DPA6q59Tw0mtgmyXRUmrQRqBZTesG-lMkl1cBmvvMeU6BLWBcGc_R6UgCKyYyTin/items/016XPCQEA5VVDIMU4BSFG3VBI37MPHZ3OE",
                "createdBy": {
                    "application": null,
                    "device": null,
                    "user": {
                        "id": "f3a5344e-dbde-48b0-be24-b5b62a243836",
                        "displayName": null
                    }
                },
                "lastModifiedBy": {
                    "application": null,
                    "device": null,
                    "user": {
                        "id": "f3a5344e-dbde-48b0-be24-b5b62a243836",
                        "displayName": null
                    }
                }
            }
        },
        {
            "distributeForStudentWork": false,
            "id": "ceb3a7e7-158e-4164-9f80-104d14884389",
            "resource": {
                "@odata.type": "#microsoft.graph.educationPowerPointResource",
                "displayName": "state diagram.pptx",
                "createdDateTime": "2021-08-27T14:42:04.8778499Z",
                "lastModifiedDateTime": "2021-08-27T14:42:04.8778499Z",
                "fileUrl": "https://graph.microsoft.com/v1.0/drives/b!DPA6q59Tw0mtgmyXRUmrQRqBZTesG-lMkl1cBmvvMeU6BLWBcGc_R6UgCKyYyTin/items/016XPCQEGRJFHRKPSI6RB3XQ6HGTB4L4FV",
                "createdBy": {
                    "application": null,
                    "device": null,
                    "user": {
                        "id": "f3a5344e-dbde-48b0-be24-b5b62a243836",
                        "displayName": null
                    }
                },
                "lastModifiedBy": {
                    "application": null,
                    "device": null,
                    "user": {
                        "id": "f3a5344e-dbde-48b0-be24-b5b62a243836",
                        "displayName": null
                    }
                }
            }
        }
    ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "List resources",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
