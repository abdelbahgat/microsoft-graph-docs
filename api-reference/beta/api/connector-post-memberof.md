---
title: "Add Connector to connectorGroup"
description: "Use this API to add a connector to a new connectorGroup."
ms.localizationpriority: medium
author: "japere"
ms.prod: "applications"
doc_type: "apiPageType"
---

# Add connector to connectorGroup

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Add a [connector](../resources/connector.md)  to a [connectorGroup](../resources/connectorgroup.md).
## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Directory.ReadWrite.All   |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported.  |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /onPremisesPublishingProfiles/applicationProxy/connectors/{id}/memberOf/$ref

```
## Request headers
| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer. Required|

## Request body
In the request body, supply a JSON representation of [connectorGroup](../resources/connectorgroup.md) object.

## Response

If successful, this method returns `201 Created` response code and [connectorGroup](../resources/connectorgroup.md) object in the response body.

## Example
##### Request
Here is an example of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create_connectorgroup_from_connector"
}-->
```http
POST https://graph.microsoft.com/beta/onPremisesPublishingProfiles/applicationProxy/connectors/{id}/memberOf/$ref
Content-type: application/json

{
  "@odata.id": "https://graph.microsoft.com/beta/onPremisesPublishingProfiles/applicationProxy/connectorGroups/{id}"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-connectorgroup-from-connector-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-connectorgroup-from-connector-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-connectorgroup-from-connector-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-connectorgroup-from-connector-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-connectorgroup-from-connector-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-connectorgroup-from-connector-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

In the request body, supply a JSON representation of [connectorGroup](../resources/connectorgroup.md) object.
##### Response
Here is an example of the response. Note: The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.connectorGroup"
} -->
```http
HTTP/1.1 201 Created
Content-type: application/json

{
  "id": "id-value",
  "name": "name-value",
  "connectorGroupType": "connectorGroupType-value",
  "isDefault": false,
  "region": "region-value"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Create connectorGroup",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->



