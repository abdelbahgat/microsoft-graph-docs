---
author: "JeremyKelley"
title: "Update bundle"
description: "Update a bundle of driveItems"
ms.localizationpriority: medium
ms.prod: "sharepoint"
doc_type: apiPageType
---

# Update bundle

Namespace: microsoft.graph

Update the metadata for a [bundle][] of [driveItems][driveItem] by ID.
You can only update the following metadata:

* Bundle name
* Album `coverImageItemId` (if applicable)

Any other change requests will be ignored.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Not supported.                             |
|Delegated (personal Microsoft account) | Files.ReadWrite, Files.ReadWrite.All   |
|Application          | Not supported.                                           |

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
PATCH /drive/items/{bundle-id}
```

## Request headers

| Name          | Description  |
|:------------- |:------------ |
| Authorization | Bearer \{token\}. Required. |
| if-match      | eTag. Optional. If this request header is included and the eTag provided does not match the current eTag on the buncle, a `412 Precondition Failed` response is returned.

## Request body

In the request body, supply the values for relevant fields that should be
updated. Existing properties that are not included in the request body
will maintain their previous values or be recalculated based on changes to other
property values. For best performance, don't include existing values that haven't changed.

## Response

If successful, this method returns a [driveItem][] resource that represents the updated bundle in the response body.

For information about error responses, see [Error responses][error-response].

## Example

This example renames a bundle.

### Request


# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "rename-bundle" } -->

```http
PATCH https://graph.microsoft.com/v1.0/drive/items/{bundle-id}
Content-Type: application/json

{
  "name": "Shared legal agreements"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/rename-bundle-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/rename-bundle-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/rename-bundle-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/rename-bundle-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/rename-bundle-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/rename-bundle-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

<!-- { "blockType": "response", "@odata.type": "microsoft.graph.driveItem", "truncated": true } -->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "id": "0123456789abc",
  "name": "Shared legal agreements",
  "bundle": {
    "childCount": 3
  }
}
```

The response object shown here might be shortened for readability.


[bundle]: ../resources/bundle.md
[driveItem]: ../resources/driveItem.md
[error-response]: /graph/errors

<!-- {
  "type": "#page.annotation",
  "description": "Update or replace the contents or properties of a bundle.",
  "keywords": "update,replace,contents,bundle",
  "section": "documentation",
	"tocPath": "Bundles/Update"
} -->


