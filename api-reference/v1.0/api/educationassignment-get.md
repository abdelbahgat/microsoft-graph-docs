---
title: "Get educationAssignment"
description: "Get the properties and relationships of an assignment."
author: "Sureshpadimi88"
ms.localizationpriority: medium
ms.prod: "education"
doc_type: apiPageType
---

# Get educationAssignment

Namespace: microsoft.graph

Get the properties and relationships of an [assignment](../resources/educationassignment.md). Only teachers, students, and applications with application permissions can perform this operation.

Students can only see assignments assigned to them; teachers and applications with application permissions can see all assignments in a class.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).


<!-- { "blockType": "permissions", "name": "educationassignment_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/educationassignment-get-permissions.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /education/classes/{id}/assignments/{id}
```

## Optional query parameters
This method supports the  `$select` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

## Request headers
| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |

## Request body
Don't supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and an [educationAssignment](../resources/educationassignment.md) object in the response body.

## Example
### Request
The following example shows a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "sampleKeys":["f4a941ff-9da6-4707-ba5b-0eae93cad0b4","3c77de7f-539b-49e1-9c96-1274f2f0ee3b"],
  "name": "get_educationassignment"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/v1.0/education/classes/f4a941ff-9da6-4707-ba5b-0eae93cad0b4/assignments/3c77de7f-539b-49e1-9c96-1274f2f0ee3b
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-educationassignment-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/get-educationassignment-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-educationassignment-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-educationassignment-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-educationassignment-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-educationassignment-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-educationassignment-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/get-educationassignment-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following example shows the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.educationAssignment"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 279

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#education/classes('f4a941ff-9da6-4707-ba5b-0eae93cad0b4')/assignments/$entity",
    "classId": "f4a941ff-9da6-4707-ba5b-0eae93cad0b4",
    "displayName": "07.30 SubmissionsUploadResource Word2",
    "closeDateTime": null,
    "dueDateTime": "2021-08-01T06:59:00Z",
    "assignDateTime": null,
    "assignedDateTime": "2021-07-30T16:01:32.5518042Z",
    "allowLateSubmissions": true,
    "resourcesFolderUrl": "https://graph.microsoft.com/v1.0/drives/b!DPA6q59Tw0mtgmyXRUmrQRqBZTesG-lMkl1cBmvvMeU6BLWBcGc_R6UgCKyYyTin/items/016XPCQECCTNQDGB5U4RCZFBXZBV5ZX24X",
    "createdDateTime": "2021-07-30T16:00:52.1918016Z",
    "lastModifiedDateTime": "2021-07-30T19:39:09.6384593Z",
    "allowStudentsToAddResourcesToSubmission": true,
    "status": "assigned",
    "notificationChannelUrl": null,
    "webUrl": "https://teams.microsoft.com/l/entity/66aeee93-507d-479a-a3ef-8f494af43945/classroom?context=%7b%22subEntityId%22%3a%22%7b%5c%22version%5c%22%3a%5c%221.0%5c%22%2c%5c%22config%5c%22%3a%7b%5c%22classes%5c%22%3a%5b%7b%5c%22id%5c%22%3a%5c%22f4a941ff-9da6-4707-ba5b-0eae93cad0b4%5c%22%2c%5c%22displayName%5c%22%3anull%2c%5c%22assignmentIds%5c%22%3a%5b%5c%223c77de7f-539b-49e1-9c96-1274f2f0ee3b%5c%22%5d%7d%5d%7d%2c%5c%22action%5c%22%3a%5c%22navigate%5c%22%2c%5c%22view%5c%22%3a%5c%22assignment-viewer%5c%22%7d%22%2c%22channelId%22%3anull%7d",
    "addedStudentAction": "none",
    "id": "3c77de7f-539b-49e1-9c96-1274f2f0ee3b",
    "instructions": {
        "content": "<div style=\"font-family: inherit; font-size: inherit; color: inherit;\">upload a word document</div>",
        "contentType": "html"
    },
    "grading": {
        "@odata.type": "#microsoft.graph.educationAssignmentPointsGradeType",
        "maxPoints": 10
    },
    "assignTo": {
        "@odata.type": "#microsoft.graph.educationAssignmentClassRecipient"
    },
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
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Get educationAssignment",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->
