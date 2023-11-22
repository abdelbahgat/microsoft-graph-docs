---
title: "List conditionalAccessPolicyCoverages"
description: "Get a list of the conditionalAccessPolicyCoverage objects and their properties."
author: "idwilliams"
ms.localizationpriority: medium
ms.prod: "multi-tenant-management"
doc_type: apiPageType
---

# List conditionalAccessPolicyCoverages
Namespace: microsoft.graph.managedTenants

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Get a list of the [conditionalAccessPolicyCoverage](../resources/managedtenants-conditionalaccesspolicycoverage.md) objects and their properties. Use this operation to list Microsoft Entra Conditional Access policy coverage for all tenants that are being managed by the multi-tenant management platform.

[!INCLUDE [national-cloud-support](../../includes/global-only.md)]

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

<!-- { "blockType": "ignored"  } // Note: Removing this line will result in the permissions autogeneration tool overwriting the table. -->
|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|Policy.Read.All, Policy.ReadWrite.ConditionalAccess, and Application.Read.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
GET /tenantRelationships/managedTenants/conditionalAccessPolicyCoverages
```

## Optional query parameters
This method supports the [OData query parameters](/graph/query-parameters) to help customize the response, including `$apply`, `$count`, `$filter`, `$orderby`, `$select`, `$skip`, and `$top`.

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [conditionalAccessPolicyCoverage](../resources/managedtenants-conditionalaccesspolicycoverage.md) objects in the response body.

## Examples

### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "list_conditionalaccesspolicycoverage"
}
-->
``` http
GET https://graph.microsoft.com/beta/tenantRelationships/managedTenants/conditionalAccessPolicyCoverages
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/list-conditionalaccesspolicycoverage-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/list-conditionalaccesspolicycoverage-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/list-conditionalaccesspolicycoverage-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/list-conditionalaccesspolicycoverage-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/list-conditionalaccesspolicycoverage-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/list-conditionalaccesspolicycoverage-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/list-conditionalaccesspolicycoverage-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/list-conditionalaccesspolicycoverage-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.managedTenants.conditionalAccessPolicyCoverage)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {
      "@odata.type": "#microsoft.graph.managedTenants.conditionalAccessPolicyCoverage",
      "id": "38227791-a88b-4fcc-81c5-58cf77668320",
      "conditionalAccessPolicyState": "enabled",
      "requiresDeviceCompliance": false,
      "latestPolicyModifiedDateTime": "2021-07-11T14:56:13.598304Z",
      "tenantDisplayName": "Consolidated Messenger"
    }
  ]
}
```
