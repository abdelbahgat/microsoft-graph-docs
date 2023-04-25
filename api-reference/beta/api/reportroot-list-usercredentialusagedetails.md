---
title: "List userCredentialUsageDetails"
description: "Get a list of userCredentialUsageDetails objects for a given tenant."
ms.localizationpriority: medium
author: "besiler"
ms.prod: "identity-and-access-reports"
doc_type: "apiPageType"
---

# List userCredentialUsageDetails (deprecated)

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]
> [!CAUTION] 
  > The user credential usage details API is deprecated and will stop returning data on April 25, 2024. Please use the new [User registration details](https://learn.microsoft.com/en-us/graph/api/resources/userregistrationdetails?view=graph-rest-beta) API

Get a list of [userCredentialUsageDetails](../resources/usercredentialusagedetails.md) objects for a given tenant. Details include user information, status of the reset, and the reason for failure.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | Reports.Read.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | Reports.Read.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /reports/userCredentialUsageDetails
```

## Optional query parameters

This function supports the optional OData query parameter **$filter**. You can apply **$filter** on one or more of the following properties of the [userCredentialUsageDetails](../resources/usercredentialusagedetails.md) resource.

| Properties | Description and example |
|:--------- |:----------- |
| feature | Filter by type of usage data that you want (registration vs reset). For example: `/reports/userCredentialUsageDetails?$filter=feature eq 'registration'`. Supported filter operators: `eq` |
| userDisplayName | Filter by user display name. For example: `/reports/userCredentialUsageDetails?$filter=userDisplayName eq 'Contoso'`. Supported filter operators: `eq` and `startswith()`. Supports case insensitive. |
| userPrincipalName  | Filter by user principal name. For example: `/reports/userCredentialUsageDetails?$filter=userPrincipalName eq 'Contoso'`.	Supported filter  operators: `eq` and `startswith()`. Supports case insensitive. |
| isSuccess | Filter by status of the activity. For example: `/reports/userCredentialUsageDetails?$filter=isSuccess eq true`. Supported filter operators: `eq` and `orderby`. |
| authMethod  | Filter by the authentication methods using during registration. For example: `/reports/userCredentialUsageDetails?$filter=authMethod eq microsoft.graph.usageAuthMethod'email'`. Supported filter operators: `eq`. |
| failureReason | Filter by failure reason (if the activity has failed). For example: `/reports/userCredentialUsageDetails?$filter=failureReason eq 'Contoso'`. Supported filter operators: `eq` and `startswith()`. Supports case insensitive. |


## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization | Bearer {token} |
| Content-Type | application/json |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [userCredentialUsageDetails](../resources/usercredentialusagedetails.md) objects in the response body.

## Examples

The following example shows how to call this API.

### Request

The following is an example of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_usercredentialusagedetails"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/beta/reports/userCredentialUsageDetails
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/get-usercredentialusagedetails-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/get-usercredentialusagedetails-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-usercredentialusagedetails-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-usercredentialusagedetails-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/get-usercredentialusagedetails-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/get-usercredentialusagedetails-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability. All the properties are returned from an actual call.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.userCredentialUsageDetails",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.context":"https://graph.microsoft.com/beta/reports/$metadata#Collection(microsoft.graph.getUserCredentialUsageDetails)",
  "value":[
    {
      "id" : "id-value",
      "feature":"registration",
      "userPrincipalName":"userPrincipalName-value",
      "userDisplayName": "userDisplayName-value",
      "isSuccess" : true,
      "authMethod": "email",
      "failureReason": "User contacted an admin after trying the email verification option",
      "eventDateTime" : "2019-04-01T00:00:00Z"
    }
  ]
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List userCredentialUsageDetails",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


