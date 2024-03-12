---
title: "RangeFormat: autofitColumns"
description: "Changes the width of the columns of the current range to achieve the best fit, based on the current data in the columns."
ms.localizationpriority: medium
author: "lumine2008"
ms.prod: "excel"
doc_type: apiPageType
---

# RangeFormat: autofitColumns

Namespace: microsoft.graph

Changes the width of the columns of the current range to achieve the best fit, based on the current data in the columns.
## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Files.ReadWrite    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
POST /me/drive/items/{id}/workbook/names/{name}/range/format/autofitColumns
POST /me/drive/root:/{item-path}:/workbook/names/{name}/range/format/autofitColumns
POST /me/drive/items/{id}/workbook/worksheets/{id|name}/range(address='<address>')/format/autofitColumns
POST /me/drive/root:/{item-path}:/workbook/worksheets/{id|name}/range(address='<address>')/format/autofitColumns
POST /me/drive/items/{id}/workbook/tables/{id|name}/columns/{id|name}/range/format/autofitColumns
POST /me/drive/root:/{item-path}:/workbook/tables/{id|name}/columns/{id|name}/range/format/autofitColumns

```
## Request headers
| Name       | Description|
|:---------------|:----------|
| Authorization  | Bearer {token}. Required. |
| Workbook-Session-Id  | Workbook session Id that determines if changes are persisted or not. Optional.|

## Request body

## Response

If successful, this method returns `200 OK` response code. It does not return anything in the response body.

## Example
Here is an example of how to call this API.
##### Request
Here is an example of the request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "rangeformat_autofitcolumns"
}-->
```http
POST https://graph.microsoft.com/v1.0/me/drive/items/{id}/workbook/names/{name}/range/format/autofitColumns
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/rangeformat-autofitcolumns-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/rangeformat-autofitcolumns-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

##### Response
Here is an example of the response. 
<!-- {
  "blockType": "response"
} -->
```http
HTTP/1.1 200 OK
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "RangeFormat: autofitColumns",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}-->

