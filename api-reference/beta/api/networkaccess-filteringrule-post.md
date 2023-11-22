---
title: "Create filteringRule"
description: "Create a new filtering rule."
author: Moti-ba
ms.localizationpriority: medium
ms.prod: global-secure-access
doc_type: apiPageType
---

# Create filteringRule
Namespace: microsoft.graph.networkaccess

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [filteringRule](../resources/networkaccess-filteringrule.md).


## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|NetworkAccessPolicy.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported.|

[!INCLUDE [rbac-global-secure-access-apis-write](../includes/rbac-for-apis/rbac-global-secure-access-apis-write.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /networkaccess/filteringPolicies/{filteringPoliciesId}/policyRules
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
Don't supply a request body for this method.

## Response

If successful, this method returns a `201 Created` response code and a [filteringRule](../resources/networkaccess-filteringrule.md) object in the response body.

## Examples

### Request
The following example shows a request.
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_filteringrule"
}
-->
``` http
POST https://graph.microsoft.com/beta/networkaccess/filteringPolicies/ac253559-37a0-4f72-b666-103420b94e38/policyRules
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.networkaccess.webCategoryFilteringRule",
    "name": "Block Alcohol",
    "ruleType": "webCategory",
    "destinations": [
        {
            "@odata.type": "#microsoft.graph.networkaccess.webCategory",
            "name": "AlcoholAndTobacco"
        }
    ]
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-filteringrule-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/create-filteringrule-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-filteringrule-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-filteringrule-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-filteringrule-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-filteringrule-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/create-filteringrule-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### Response
The following example shows the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.networkaccess.filteringRule"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#networkAccess/filteringPolicies('ac253559-37a0-4f72-b666-103420b94e38')/policyRules/$entity",
    "@odata.type": "#microsoft.graph.networkaccess.webCategoryFilteringRule",
    "id": "0d7ce7af-fbed-4751-8fed-8c184b751d0b",
    "name": "BlockStreaming",
    "ruleType": "webCategory",
    "destinations": [
        {
            "@odata.type": "#microsoft.graph.networkaccess.webCategory",
            "name": "StreamingMediaAndDownloads",
            "displayName": "Streaming Media + Music and Streaming Audio",
            "group": "HighBandwidth"
        }
    ]
}
```

