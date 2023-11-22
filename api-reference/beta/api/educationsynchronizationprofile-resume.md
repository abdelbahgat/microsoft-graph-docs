---
title: "Resume sync on an educationSynchronizationProfile"
description: "Resume the sync of a specific school data synchronization profile in the tenant."
author: "mmast-msft"
ms.localizationpriority: medium
ms.prod: "education"
doc_type: apiPageType
---

# Resume sync on an educationSynchronizationProfile

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Resume the sync of a specific school data [synchronization profile](../resources/educationsynchronizationprofile.md) in the tenant.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "educationsynchronizationprofile_resume" } -->
[!INCLUDE [permissions-table](../includes/permissions/educationsynchronizationprofile-resume-permissions.md)]

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /education/synchronizationProfiles/{id}/resume
```

## Request headers
| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer {token}. Required.  |

## Request body
Don't supply a request body for this method.
## Response
If successful, this method returns a `200 OK` response code.

## Example
##### Request
The following example shows a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "post_educationSynchronizationProfile_resume"
}-->
```http
POST https://graph.microsoft.com/beta/education/synchronizationProfiles/{id}/resume
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/post-educationsynchronizationprofile-resume-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/post-educationsynchronizationprofile-resume-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/post-educationsynchronizationprofile-resume-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/post-educationsynchronizationprofile-resume-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/post-educationsynchronizationprofile-resume-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/post-educationsynchronizationprofile-resume-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/post-educationsynchronizationprofile-resume-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/post-educationsynchronizationprofile-resume-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

##### Response

There is no response body.

<!-- {
  "blockType": "response",
  "name": "post_educationSynchronizationProfile_resume"
}-->
```http
HTTP/1.1 200 OK
```
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79 
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Example",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->


