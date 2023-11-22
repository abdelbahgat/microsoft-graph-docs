---
title: "Restart synchronizationJob"
description: "Restart the synchronization job, forcing it to reprocess all the objects in the directory. Optionally clears existing synchronization state and previous errors."
ms.localizationpriority: medium
doc_type: apiPageType
author: "ArvindHarinder1"
ms.prod: "applications"
---

# Restart synchronizationJob

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Restart a stopped synchronization job, forcing it to reprocess all the objects in the directory. Optionally clears existing the synchronization state and previous errors.

[!INCLUDE [national-cloud-support](../../includes/global-us.md)]

## Permissions
Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "synchronization_synchronizationjob_restart" } -->
[!INCLUDE [permissions-table](../includes/permissions/synchronization-synchronizationjob-restart-permissions.md)]

[!INCLUDE [rbac-synchronization-apis](../includes/rbac-for-apis/rbac-synchronization-apis.md)]

## HTTP Request

`{servicePrincipalId}` refers to the **id** of the service principal object. **id** is referred to as the **Object ID** of the enterprise application in app registrations in the Microsoft Entra admin center.

You can address the service principal using either its **id** or **appId**. **id** and **appId** are referred to as the **Object ID** and **Application (Client) ID**, respectively, in app registrations in the Microsoft Entra admin center.
<!-- { "blockType": "ignored" } -->
```http
POST /servicePrincipals/{servicePrincipalId}/synchronization/jobs/{jobId}/restart
POST /servicePrincipals(appId='{appId}')/synchronization/jobs/{jobId}/restart
```

## Request headers

| Name           | Type    | Description|
|:---------------|:--------|:-----------|
| Authorization  | string  | Bearer {token}. Required. |

## Request body

In the request body, provide a JSON object with the following parameter.

| Parameter     | Type      | Description    |
|:--------------|:----------|:---------------|
|criteria       |[synchronizationJobRestartCriteria](../resources/synchronization-synchronizationjobrestartcriteria.md) |Restart criteria|

## Response

If successful, returns a `204 No Content` response. It doesn't return anything in the response body.

## Example

### Request
The following is an example of a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "synchronizationjob_restart"
}-->
```http
POST https://graph.microsoft.com/beta/servicePrincipals/{id}/synchronization/jobs/{jobId}/restart
Authorization: Bearer <token>
Content-type: application/json

{
   "criteria": {
       "resetScope": "Watermark, Escrows, QuarantineState"
   }
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/synchronizationjob-restart-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/synchronizationjob-restart-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/synchronizationjob-restart-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/synchronizationjob-restart-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/synchronizationjob-restart-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/synchronizationjob-restart-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/synchronizationjob-restart-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/synchronizationjob-restart-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following is an example of a response.

<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 204 No Content
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "synchronizationJob: restart",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
    "Error: microsoft.graph.microsoft.graph/servicePrincipals:
      /servicePrincipals/{var}/synchronization/jobs/{var}/restart
      Uri path requires navigating into unknown object hierarchy: missing property 'jobs' on 'synchronization'. Possible issues:
       1) Doc bug where 'jobs' isn't defined on the resource.
       2) Doc bug where 'jobs' is an example key and should instead be replaced with a placeholder like {item-id} or declared in the sampleKeys annotation.
       3) Doc bug where 'synchronization' is supposed to be an entity type, but is being treated as a complex because it (and its ancestors) are missing the keyProperty annotation."
  ]
}
-->


