---
title: "Get profilePhoto"
description: "Get the specified profilePhoto or its metadata (profilePhoto properties)."
ms.localizationpriority: medium
author: "kevinbellinger"
ms.prod: "people"
doc_type: apiPageType
---

# Get profilePhoto

Namespace: microsoft.graph

Get the specified [profilePhoto](../resources/profilephoto.md) or its metadata (**profilePhoto** properties).

The supported sizes of HD photos on Microsoft 365 are as follows: 48x48, 64x64, 96x96, 120x120, 240x240,
360x360, 432x432, 504x504, and 648x648. Photos can be any dimension if they are stored in Azure Active Directory.

You can get the metadata of the largest available photo, or specify a size to get the metadata for that photo size.
If the size you request is not available, you can still get a smaller size that the user has uploaded and made available.
For example, if the user uploads a photo that is 504x504 pixels, all but the 648x648 size of photo will be available for download.

## Permissions

One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

### To retrieve the profile photo of a contact

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account)      |   Contacts.Read, Contacts.ReadWrite           |
|Delegated (personal Microsoft account)      |   Contacts.Read, Contacts.ReadWrite            |
|Application      |    Contacts.Read, Contacts.ReadWrite           |

### To retrieve the profile photo of a group

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account)      |   Group.Read.All, Group.ReadWrite.All           |
|Delegated (personal Microsoft account)      |   Not supported.            |
|Application      |    Group.Read.All, Group.ReadWrite.All           |

### To retrieve the profile photo of a team

| Permission Type | Permissions (from least to most privileged)                   |
| --------------- | ------------------------------------------------------------- |
| Delegated (work or school account)        | TeamReadBasicAll, TeamSettingsReadAll, TeamSettingsReadWriteAll |
| Delegated (personal Microsoft account)    | Not supported.                      |
| Application                               | TeamReadBasicAll, TeamSettingsReadAll, TeamSettingsReadWriteAll |

### To retrieve the profile photo of a user

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account)      |   User.Read, User.ReadBasic.All, User.Read.All, User.ReadWrite, User.ReadWrite.All           |
|Delegated (personal Microsoft account)      |   User.Read, User.ReadWrite            |
|Application      |    User.Read.All, User.ReadWrite.All           |

> [!NOTE]
> 
> 1. Metadata operation is not supported for personal Microsoft accounts.
> 2. There is currently a [known issue](/graph/known-issues#groups) with accessing group photos using application permissions.
> 3. Retrieving a user's photo using the Microsoft Graph API is currently not supported in Azure AD B2C tenants.

## HTTP request

### Get the photo
<!-- { "blockType": "ignored" } -->

```http
GET /me/photo/$value
GET /users/{id | userPrincipalName}/photo/$value
GET /groups/{id}/photo/$value
GET /me/contacts/{id}/photo/$value
GET /users/{id | userPrincipalName}/contacts/{id}/photo/$value
GET /me/contactfolders/{contactFolderId}/contacts/{id}/photo/$value
GET /users/{id | userPrincipalName}/contactfolders/{contactFolderId}/contacts/{id}/photo/$value
GET /team/{id}/photo/$value
```

### Get the metadata of the photo
<!-- { "blockType": "ignored" } -->

```http
GET /me/photo
GET /me/photos
GET /users/{id | userPrincipalName}/photo
GET /groups/{id}/photo
GET /me/contacts/{id}/photo
GET /users/{id | userPrincipalName}/contacts/{id}/photo
GET /me/contactfolders/{contactFolderId}/contacts/{id}/photo
GET /users/{id | userPrincipalName}/contactfolders/{contactFolderId}/contacts/{id}/photo
GET /team/{id}/photo
```

### Get the metadata for a specific photo size
<!-- { "blockType": "ignored" } -->

```http
GET /me/photos/{size}
GET /users/{id | userPrincipalName}/photos/{size}
GET /groups/{id}/photos/{size}
```

## Path parameters

|Parameter|Type|Description|
|:-----|:-----|:-----|
|size  |String  | A photo size. The supported sizes of HD photos on Microsoft 365 are as follows: 48x48, 64x64, 96x96, 120x120, 240x240, 360x360, 432x432, 504x504, and 648x648. Photos can be any dimension if they are stored in Azure Active Directory. |

## Optional query parameters
This method supports the [OData query parameters](/graph/query-parameters) to help customize the response.

## Request headers

| Name       | Type | Description|
|:-----------|:------|:----------|
| Authorization  | string  | Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response
### Response for getting the photo
If successful, this method returns a `200 OK` response code and binary data of the requested photo.  If no photo exists, the operation returns `404 Not Found`.
### Response for getting the metadata of the photo
If successful, this method returns a `200 OK` response code and [profilePhoto](../resources/profilephoto.md) object in the response body.
## Examples

### Example 1: Get the photo for the signed-in user in the largest available size
#### Request
<!-- {
  "blockType": "ignored"
}-->

```http
GET https://graph.microsoft.com/v1.0/me/photo/$value
```

#### Response
Contains the binary data of the requested photo. The HTTP response code is 200.

### Example 2: Get the 48x48 photo for the signed-in user
#### Request
<!-- {
  "blockType": "ignored"
}-->

```http
GET https://graph.microsoft.com/v1.0/me/photos/48x48/$value
Content-Type: image/jpg
```

#### Response
Contains the binary data of the requested 48x48 photo. The HTTP response code is 200.

### Example 3: Get the metadata of the user photo of the signed-in user
#### Request
<!-- {
  "blockType": "ignored"
}-->

```http
GET https://graph.microsoft.com/v1.0/me/photo
```

#### Response

The following response data shows the photo metadata.

>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "ignored"
}-->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#Me/photo/$entity",
    "@odata.id": "https://graph.microsoft.com/v1.0/users('ddfcd489-628b-7d04-b48b-20075df800e5@1717622f-1d94-c0d4-9d74-f907ad6677b4')/photo",
    "@odata.mediaContentType": "image/jpeg",
    "@odata.mediaEtag": "\"BA09D118\"",
    "id": "240x240",
    "width": 240,
    "height": 240
}
```

The following response data shows the contents of a response when a photo hasn't already been uploaded for the user.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "ignored"
}-->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#Me/photo/$entity",
    "@odata.id": "https://graph.microsoft.com/v1.0/users('ddfcd489-628b-7d04-b48b-20075df800e5@1717622f-1d94-c0d4-9d74-f907ad6677b4')/photo",
    "@odata.mediaContentType": "image/gif",
    "@odata.mediaEtag": "",
    "id": "1x1",
    "width": 1,
    "height": 1
}
```
### Example 4: Get the metadata of the team photo

#### Request

Here is an example of the request to get the metadata of the team photo.

<!-- {
  "blockType": "ignored",
  "name": "get_team_photo_metadata"
}-->
```http
GET https://graph.microsoft.com/v1.0/teams/172b0cce-e65d-44ce-9a49-91d9f2e8491e/photo
```

#### Response

Here is an example of the response.

> **Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response"
} -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#teams('172b0cce-e65d-44ce-9a49-91d9f2e8491e')/photo/$entity",
    "@odata.id": "https://graph.microsoft.com/v1.0/teams('172b0cce-e65d-44ce-9a49-91d9f2e8491e')/photo",
    "@odata.mediaContentType": "image/jpeg",
    "@odata.mediaEtag": "\"BA09D118\"",
    "id": "240X240",
    "width": 240,
    "height": 240
}
```

### Example 5: Get the team photo's binary data

Here is an example of the request to get the team photo's binary data.

#### Request

<!-- {
  "blockType": "ignored",
  "name": "get_team_photo"
}-->
```http
GET https://graph.microsoft.com/v1.0/teams/172b0cce-e65d-44ce-9a49-91d9f2e8491e/photo/$value
```

#### Response

Contains the binary data of the requested photo. The HTTP response code is 200.

## Using the binary data of the requested photo

When you use the `/photo/$value` endpoint to get the binary data for a profile photo, you'll need to convert the data into a base-64 string in order to add it as an email attachment. Here is an example in JavaScript of how to create an array that you can pass as the value of the `Attachments` parameter of an [Outlook Message](user-post-messages.md).

```java
const attachments = [{
  '@odata.type': '#microsoft.graph.fileAttachment',
  ContentBytes: file.toString('base64'),
  Name: 'mypic.jpg'
}];
```

See the [Microsoft Graph Connect Sample for Node.js](https://github.com/microsoftgraph/nodejs-connect-rest-sample) for an implementation of this example.

If you want to display the image on a web page, create an in-memory object from the image and make that object the source of an image element. Here is an example in JavaScript of this operation.

```javascript
const url = window.URL || window.webkitURL;
const blobUrl = url.createObjectURL(image.data);
document.getElementById(imageElement).setAttribute("src", blobUrl);
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "Get photo",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

