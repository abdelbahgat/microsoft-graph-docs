---
title: Update taskDefinition
description: Update a task definition.
author: braedenp-msft
ms.localizationpriority: medium
ms.prod: cloud-printing
doc_type: apiPageType
---

# Update taskDefinition

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update a task definition.

For details about how to use this API to add pull printing support to Universal Print, see [Extending Universal Print to support pull printing](/graph/universal-print-concept-overview#extending-universal-print-to-support-pull-printing).

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

In addition to the following permissions, the user's tenant must have an active Universal Print subscription.

|Permission type | Permissions (from least to most privileged) |
|:---------------|:--------------------------------------------|
|Delegated (work or school account)| Not supported. |
|Delegated (personal Microsoft account)|Not Supported.|
|Application| PrintTaskDefinition.ReadWrite.All |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
PATCH /print/taskDefinitions/{id}
```

## Request headers
| Name      |Description|
|:----------|:----------|
| Authorization | Bearer {token}. Required. |
| Content-type  | application/json. Required.|

## Request body
In the request body, supply the values for the relevant [printTaskDefinition](../resources/printtaskdefinition.md) fields that should be updated. Existing properties that are not included in the request body will maintain their previous values or be recalculated based on changes to other property values. For best performance, don't include existing values that haven't changed.

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|displayName|String|The name of the printTaskDefinition.|
|createdBy|String|Information about the app that created the task definition. Only the `createdBy.displayName` property can be updated.|

## Response
If successful, this method returns a `200 OK` response code and an updated [printTaskDefinition](../resources/printtaskdefinition.md) object in the response body.
## Example
### Request
The following is an example of the request.


# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "print_update_taskdefinition"
}-->
```msgraph-interactive
PATCH https://graph.microsoft.com/beta/print/taskDefinitions/fab143fd-ee61-4358-8558-2c7dee953982
Content-type: application/json

{
  "displayName": "Test TaskDefinitionName",
  "createdBy": {
    "displayName": "Requesting App Display Name"
  }
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/print-update-taskdefinition-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/print-update-taskdefinition-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/print-update-taskdefinition-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/print-update-taskdefinition-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/print-update-taskdefinition-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/print-update-taskdefinition-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


---

### Response
The following is an example of the response.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.printTaskDefinition"
}
-->
```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#print/taskDefinitions/$entity",
  "id": "fab143fd-ee61-4358-8558-2c7dee953982",
  "displayName": "Test TaskDefinitionName",
  "createdBy": {
    "appId" : "479688a0-cc3a-4993-ab24-54c7c80b047e",
    "displayName": "Requesting App Display Name"
  }
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Update taskDefinition",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->


