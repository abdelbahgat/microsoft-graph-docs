---
title: "List appliesTo"
description: "Get a list of directoryObject objects that a tokenIssuancePolicy object has been applied to."
ms.localizationpriority: medium
author: "luleonpla"
ms.prod: "identity-and-sign-in"
doc_type: "apiPageType"
---

# List appliesTo

Namespace: microsoft.graph



Get a list of [directoryObject](../resources/directoryObject.md) objects that a [tokenIssuancePolicy](../resources/tokenissuancepolicy.md) object has been applied to. The tokenIssuancePolicy can only be applied to [application](../resources/application.md).

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged) |
|:---------------------------------------|:--------------------------------------------|
| Delegated (work or school account)     | Policy.Read.All and Application.Read.All, Policy.ReadWrite.ApplicationConfiguration and Application.Read.All, Directory.Read.All |
| Delegated (personal Microsoft account) | Not supported. |
| Application                            | Policy.Read.All and Application.Read.All, Policy.ReadWrite.ApplicationConfiguration and Application.Read.All, Directory.Read.All |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /policies/tokenIssuancePolicies/{id}/appliesTo
```

## Optional query parameters

This method supports the `$expand`, `$select`, and `$top` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters). When using `$expand`, make sure your app requests permissions to read the expanded objects.

## Request headers

| Name      |Description|
|:----------|:----------|
| Authorization | Bearer {token}. Required. |

## Request body

Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [directoryObject](../resources/directoryobject.md) objects in the response body.

## Examples

### Request

The following is an example of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_appliesto_3"
}-->

```msgraph-interactive
GET https://graph.microsoft.com/v1.0/policies/tokenIssuancePolicies/{id}/appliesTo
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-appliesto-3-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-appliesto-3-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following is an example of the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.directoryObject",
  "isCollection": true
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "value": [
    {
      "id": "id-value",
      "deletedDateTime": "datetime-value"
    }
  ]
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List appliesTo",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

