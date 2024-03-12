---
title: "accessReviewInstance: batchRecordDecisions"
description: "Enables reviewers to review all accessReviewInstanceDecisionItem objects in batches."
author: "jyothig123"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: apiPageType
---

# accessReviewInstance: batchRecordDecisions
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Enables reviewers to review all [accessReviewInstanceDecisionItem](../resources/accessreviewinstancedecisionitem.md) objects in batches by using **principalId**, **resourceId**, or neither.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|AccessReview.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported|
|Application|AccessReview.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
POST /me/pendingAccessReviewInstances/{accessReviewInstanceId}/batchRecordDecisions
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

|Parameter|Type|Description|
|:---|:---|:---|
| decision  | String | Access decision for the entity being reviewed. Possible values are: `Approve`, `Deny`, `NotReviewed`, `DontKnow`. Required.  |
|  justification | String | Context of the review provided to admins. Required if **justificationRequiredOnApproval** is `True` on the **accessReviewScheduleDefinition**.  |
|principalId|String|If supplied, all the **accessReviewInstanceDecisionItems** with matching **principalId** will be reviewed in this batch. If not supplied, all **principalIds** will be reviewed.|
|resourceId|String|If supplied, all the **accessReviewInstanceDecisionItems** with matching **resourceId** will be reviewed in this batch. If not supplied, all **resourceIds** will be reviewed.|



## Response

If successful, this action returns a `204 No Content` response code.

## Examples

### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "accessreviewinstance_batchrecorddecisions"
}
-->
``` http
POST https://graph.microsoft.com/beta/me/pendingAccessReviewInstances/{accessReviewInstanceId}/batchRecordDecisions
Content-Type: application/json

{
  "decision": "Approve",
  "justification": "All principals with access need continued access to the resource (Marketing Group) as all the principals are on the marketing team",
  "resourceId": "a5c51e59-3fcd-4a37-87a1-835c0c21488a"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/accessreviewinstance-batchrecorddecisions-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/accessreviewinstance-batchrecorddecisions-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/accessreviewinstance-batchrecorddecisions-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/accessreviewinstance-batchrecorddecisions-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/accessreviewinstance-batchrecorddecisions-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/accessreviewinstance-batchrecorddecisions-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
<!-- {
  "blockType": "response",
  "truncated": true
}
-->
``` http
HTTP/1.1 204 No Content
```
