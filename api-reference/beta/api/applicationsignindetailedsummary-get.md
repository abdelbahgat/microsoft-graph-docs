---
title: "Get applicationSignInDetailedSummary"
description: "Retrieve the properties and relationships of an applicationSignInDetailSummary object."
ms.localizationpriority: medium
author: "besiler"
ms.prod: "identity-and-access-reports"
doc_type: apiPageType
---

# Get applicationSignInDetailedSummary

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Retrieve the properties and relationships of an [applicationSignInDetailSummary](../resources/applicationsignindetailedsummary.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type                        | Permissions (from least to most privileged)              |
|:--------------------------------------|:---------------------------------------------------------|
|Delegated (work or school account)     | Reports.Read.All |
|Delegated (personal Microsoft account) | Not supported. |
|Application                            | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
``` http
GET /reports/applicationSignInDetailedSummary/{id}
```

## Optional query parameters

This method supports the [OData query parameters](/graph/query-parameters) to help customize the response.

## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization | Bearer {code} |

## Request body
Do not supply a request body for this method.

## Response
If successful, this method returns a `200 OK` response code and an [applicationSignInDetailedSummary](../resources/applicationsignindetailedsummary.md) object in the response body.

## Example

### Request
The following is an example of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_applicationsignindetailedsummary"
}-->
```msgraph-interactive
GET https://graph.microsoft.com/beta/reports/applicationSignInDetailedSummary/{id}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-applicationsignindetailedsummary-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-applicationsignindetailedsummary-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-applicationsignindetailedsummary-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-applicationsignindetailedsummary-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-applicationsignindetailedsummary-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-applicationsignindetailedsummary-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response
The following is an example of the response. 

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.applicationSignInDetailedSummary"
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "id-value",
  "appId": "appId-value",
  "appDisplayName": "appDisplayName-value",
  "status": {
    "errorCode": 99,
    "failureReason": "failureReason-value",
    "additionalDetails": "additionalDetails-value"
  },
  "signInCount": 99,
  "aggregatedEventDateTime": "datetime-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get applicationSignInDetailedSummary",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->


