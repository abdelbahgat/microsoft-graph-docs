---
title: "driveItem: preview"
description: "This action allows you to obtain short-lived embeddable URLs for an item in order to render a temporary preview."
ms.localizationpriority: medium
ms.prod: "sharepoint"
doc_type: apiPageType
author: "JeremyKelley"
---

# driveItem: preview

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

This action allows you to obtain short-lived embeddable URLs for an item in order to render a temporary preview.

If you want to obtain long-lived embeddable links, use the [createLink][] API instead.

> **Note:** The **preview** action is currently only available on SharePoint and OneDrive for Business.

[createLink]: driveitem-createlink.md

## Permissions

One of the following permissions is required to call this API.
To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)
|:---------------------------------------|:-------------------------------------------
| Delegated (work or school account)     | Files.Read, Files.ReadWrite, Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All
| Delegated (personal Microsoft account) | Not supported.
| Application                            | Files.Read.All, Files.ReadWrite.All, Sites.Read.All, Sites.ReadWrite.All

## HTTP request

<!-- { "blockType": "ignored" } -->

```http
POST /drives/{driveId}/items/{itemId}/preview
POST /groups/{groupId}/drive/items/{itemId}/preview
POST /me/drive/items/{itemId}/preview
POST /sites/{siteId}/drive/items/{itemId}/preview
POST /users/{userId}/drive/items/{itemId}/preview
POST /shares/{shareId}/driveItem/preview
```

## Request body

The body of the request defines properties of the embeddable URL your application is requesting.
The request should be a JSON object with the following properties.

|   Name      |  Type         | Description
|:------------|:--------------|:-----------------------------------------------
| viewer      | string        | Optional. Preview app to use. `onedrive` or `office`. If null, a suitable viewer will be chosen automatically.
| chromeless  | boolean       | Optional. If `true` (default), the embedded view will not include any controls.
| allowEdit   | boolean       | Optional. If `true`, the file can be edited from the embedded UI.
| page        | string/number | Optional. Page number of document to start at, if applicable. Specified as string for future use cases around file types such as ZIP.
| zoom        | number        | Optional. Zoom level to start at, if applicable.

## Response

```json
{
    "getUrl": "https://www.onedrive.com/embed?foo=bar&bar=baz",
    "postParameters": "param1=value&param2=another%20value",
    "postUrl": "https://www.onedrive.com/embed_by_post"
}
```

The response will be a JSON object containing the following properties:

| Name           | Type   | Description
|:---------------|:-------|:---------------------------------------------------
| getUrl         | string | URL suitable for embedding using HTTP GET (iframes, etc.)
| postUrl        | string | URL suitable for embedding using HTTP POST (form post, JS, etc.)
| postParameters | string | POST parameters to include if using postUrl

Either getUrl, postUrl, or both might be returned depending on the current state of embed support for the specified options.

postParameters is a string formatted as `application/x-www-form-urlencoded`, and if performing a POST to the postUrl the content-type should be set accordingly. For example:
```
POST https://www.onedrive.com/embed_by_post
Content-Type: application/x-www-form-urlencoded

param1=value&param2=another%20value
```

### Viewers

>**Note:** This parameter is deprecated and will not be made available on the v1.0 endpoint.

The following values are allowed for the **viewer** parameter.

| Type value | Description
|:-----------|:----------------------------------------------------------------
| (null)     | Chooses an appropriate app for rendering the file. In most cases this will use the `onedrive` previewer, but may vary by file type.
| `onedrive` | Use the OneDrive previewer app to render the file.
| `office`   | Use the web version of Office to render the file. Only valid for Office documents.

### Chrome vs chromeless
>**Note:** This parameter is deprecated and will not be made available on the v1.0 endpoint.

If `chromeless` is true, the preview will be a bare rendering of the file.
Otherwise, there may be additional toolbars/buttons displayed for interacting with the document/view.

### View/edit
>**Note:** This parameter is deprecated and will not be made available on the v1.0 endpoint.

If `allowEdit` is true, the document can be modified by user interaction with the embedded preview.
This capability may not be available for all preview apps or file types.

### Page/zoom

The `page` and `zoom` options might not be available for all preview apps, but will be applied if the preview app supports it.


