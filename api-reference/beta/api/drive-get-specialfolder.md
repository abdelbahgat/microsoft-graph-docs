---
author: JeremyKelley
description: "Use the special collection to access a special folder by name."
title: Get Special Folders
ms.localizationpriority: medium
ms.prod: "sites-and-lists"
doc_type: apiPageType
---
# Get a special folder by name

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Use the special collection to access a special folder by name.

Special folders provide simple aliases to access well-known folders in OneDrive without the need to look up the folder by path (which would require localization), or reference the folder with an ID. If a special folder is renamed or moved to another location within the drive, this syntax will continue to find that folder.

Special folders are automatically created the first time an application attempts to write to one, if it doesn't already exist. If a user deletes one, it is recreated when written to again.

> **Note:**  If you have read-only permissions and request a special folder that doesn't exist, you'll receive a `403 Forbidden` error.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|            Permission type             |                                           Permissions (from least to most privileged)                                            |
| :------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------- |
| Delegated (work or school account)     | Files.Read, Files.ReadWrite, Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All                            |
| Delegated (personal Microsoft account) | Files.ReadWrite.AppFolder, Files.Read, Files.ReadWrite, Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All |
| Application                            | Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All                                                         |

## HTTP Request

<!-- { "blockType": "ignored"} -->

```http
GET /me/drive/special/{name}
```

### Special folder names
[!INCLUDE [files-special-folder-list](../includes/files-special-folder-list.md)]

### Optional query parameters

This method supports the `$expand` and `$select` [OData query parameters](/graph/query-parameters) to customize the response.

## Response

This method returns a `200 OK` response code and a [driveItem](../resources/driveitem.md) object in the response body.

You can use this method of addressing a special folder inline with additional calls to properties or relationships on the driveItem.

## Examples 

### Example 1: Get special folder by name

#### Request

# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "get-special-folder" } -->

```msgraph-interactive
GET /me/drive/special/{name}
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-special-folder-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-special-folder-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response
<!-- { "blockType": "response", "@odata.type": "microsoft.graph.driveItem", "truncated": true } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "id": "0123456789abc",
  "name": "Documents",
  "eTag": "012345819293.1",
  "specialFolder": {
    "name": "documents"
  }
}
```


### Example 2: Get children of a special folder

To request the children of a special folder, you can request the `children`
collection or use the [expand](/graph/query-parameters) option to expand the children collection.

#### Request

# [HTTP](#tab/http)
<!-- { "blockType": "request", "name": "get-special-children", "scopes": "files.read" } -->

```msgraph-interactive
GET /me/drive/special/{name}/children
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-special-children-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-special-children-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

<!-- { "blockType": "response", "@odata.type": "microsoft.graph.driveItem", "isCollection": true, "truncated": true} -->

```http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "value": [
    {"name": "myfile.jpg", "size": 2048 },
    {"name": "Documents", "folder": { "childCount": 4} },
    {"name": "Photos", "folder": { "childCount": 203} },
    {"name": "my sheet(1).xlsx", "size": 197 }
  ]
}
```

## Remarks

> **Note:** DriveItems with the `specialFolder` facet indicate the item is a special folder and can be accessed via the `special` collection.

If your app has read-only permissions, the request to get a special folder or
the children of a special folder may fail with a `404 Not Found` or a `403 Forbidden`
error if the special folder does not already exist.

<!--
{
  "type": "#page.annotation",
  "description": "Access known folders in OneDrive through the special folder collection",
  "keywords": "known folders",
  "section": "documentation",
  "tocPath": "OneDrive/Drive/Special folders",
  "suppressions": [
  ]
}
-->

