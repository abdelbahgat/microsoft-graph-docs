---
title: "Update subjectRightsRequest"
description: "Update the properties of a subjectRightsRequest object."
author: "skadam-msft"
ms.localizationpriority: medium
ms.prod: "compliance"
doc_type: apiPageType
---

# Update subjectRightsRequest
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [subjectRightsRequest](../resources/subjectRightsRequest.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|SubjectRightsRequest.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|Not supported|

## HTTP request

[!INCLUDE [subject-rights-request-privacy-deprecate](../../includes/subject-rights-request-privacy-deprecate.md)]

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /security/subjectRightsRequests/{subjectRightsRequestId}
PATCH /privacy/subjectRightsRequests/{subjectRightsRequestId}
```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [subjectRightsRequest](../resources/subjectRightsRequest.md) object.

The following table shows the properties that are required when you update the [subjectRightsRequest](../resources/subjectRightsRequest.md).

|Property|Type|Description|
|:---|:---|:---|
|description|String|Updated description for the request.|
|displayName|String|Updated name of the request.|
|internalDueDateTime|DateTimeOffset|Updated internal due date for the request.|

## Response

If successful, this method returns a `200 OK` response code and an updated [subjectRightsRequest](../resources/subjectRightsRequest.md) object in the response body.

## Examples

### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "update_subjectRightsRequest"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/privacy/subjectRightsRequests/{subjectRightsRequestId}
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.subjectRightsRequest",
    "internalDueDateTime": "2021-08-30T00:00:00Z"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/update-subjectrightsrequest-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/update-subjectrightsrequest-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/update-subjectrightsrequest-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/update-subjectrightsrequest-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/update-subjectrightsrequest-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.subjectRightsRequest"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
    "displayName": "Updated case name for Diego Siciliani",
    "description": "This is an updated case",
    "internalDueDateTime": "2022-07-20T22:42:28Z"
}
```

