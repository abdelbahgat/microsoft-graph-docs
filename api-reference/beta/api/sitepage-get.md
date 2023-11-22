---
author: sangle7
description: "Returns the metadata for a sitePage in the site pages list in a site."
ms.date: 03/15/2018
title: Get sitePage
ms.localizationpriority: medium
ms.prod: "sharepoint"
doc_type: apiPageType
---

# Get SitePage

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Returns the metadata for a [sitePage][] in the site pages [list][] in a [site][].

[sitePage]: ../resources/sitePage.md
[list]: ../resources/list.md
[site]: ../resources/site.md

[!INCLUDE [national-cloud-support](../../includes/all-clouds.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "sitepage_get" } -->
[!INCLUDE [permissions-table](../includes/permissions/sitepage-get-permissions.md)]


## HTTP request

<!-- { "blockType": "ignored" } -->

```http
GET /sites/{site-id}/pages/{page-id}/microsoft.graph.sitePage
```

## Optional query parameters

This method supports the `$select` and `$expand` OData query parameters to help customize the response. For general information, see [OData query parameters](/graph/query-parameters).

You can use the `$expand=canvasLayout` query string parameter to include the content of an item when retrieving the metadata of an item if the item has a **=canvasLayout** relationship.


## Request headers

| Name       | Description |
|:---------------|:--------|
|Authorization|Bearer {token}. Required.|
| Content-Type  | application/json. Required. |
| Accept |application/json;odata.metadata=none. Optional. Removes all OData metadata from the response. We recommend including this header when the response will be used in another request. |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200` and a [sitePage](../resources/sitepage.md) object in the response body.


## Examples

### Example 1: Get a page in the site pages list of a site
#### Request

# [HTTP](#tab/http)

<!-- { "blockType": "request", "name": "get-page", "scopes": "sites.read.all", "tags": "service.sharepoint" } -->

```msgraph-interactive
GET /sites/{site-id}/pages/{page-id}/microsoft.graph.sitePage
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-page-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-page-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

<!-- { "blockType": "response", "@odata.type": "microsoft.graph.sitePage", "truncated": true } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
  "@odata.type": "microsoft.graph.sitePage",
  "description": "Here's the page description",
  "id": "65e59907-59d5-44ff-a038-7c0bf3098c01",
  "name": "Home.aspx",
  "webUrl": "SitePages/Home.aspx",
  "title": "Organization Home",
  "thumbnailWebUrl": "https://cdn.hubblecontent.osi.office.net/m365content/publish/00210d24-bba0-42e6-9a31-1d452a95dd75/thumbnails/large.jpg?file=163352059.jpg",
  "promotionKind": "page",
  "pageLayout": "home",
  "showComments": true,
  "showRecommendedPages": false,
  "createdBy": {
    "user": {
        "displayName": "Rahul Mittal",
        "email": "rahmit@contoso.com"
    }
  },
  "lastModifiedBy": {
    "user": {
        "displayName": "Rahul Mittal",
        "email": "rahmit@contoso.com"
    }
  },
  "publishingState": {
    "level": "published",
    "versionId": "1.0"
  },
  "reactions": {
    "commentCount": 1
  }
}
```

### Example 2: Get a page using select and expand

#### Request

With `select` and `expand` statements, you can retrieve sitePage metadata and page content in a single request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "get_sitePage"
}
-->

```msgraph-interactive
GET /sites/{site-id}/pages/{page-id}/microsoft.graph.sitePage
```

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/get-sitepage-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/get-sitepage-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

#### Response

The following example shows the response.

<!-- { "blockType": "response", "@odata.type": "microsoft.graph.sitePage", "truncated": true } -->

```http
HTTP/1.1 200 OK
Content-type: application/json

{
    "@odata.etag": "\"{F45354CB-D634-45DF-8B88-2B4E96A1DC45},8\"",
    "description": "Reiciendis placeat dolores.Mollitia veniam tempora tempora quidem voluptatum.Quos animi maiores facilis.Dolores officiis consequatur provident beatae deleniti accusamus magni quam tenetur.",
    "eTag": "\"{F45354CB-D634-45DF-8B88-2B4E96A1DC45},8\"",
    "id": "f45354cb-d634-45df-8b88-2b4e96a1dc45",
    "lastModifiedDateTime": "2023-04-16T10:01:41Z",
    "name": "Electronic Convertible.aspx",
    "webUrl": "SitePages/Electronic Convertible.aspx",
    "title": "Electronic Convertible",
    "pageLayout": "article",
    "thumbnailWebUrl": "https://media.akamai.odsp.cdn.office.net/_layouts/15/images/sitepagethumbnail.png",
    "promotionKind": "page",
    "showComments": false,
    "showRecommendedPages": true,
    "contentType": {
        "id": "0x0101009D1CB255DA76424F860D91F20E6C4118009E6554A5E299E84FB2E07731DD6C6D4A",
        "name": "Site Page"
    },
    "createdBy": {
        "user": {
            "displayName": "admin_contoso",
            "email": "admin@contoso.onmicrosoft.com"
        }
    },
    "lastModifiedBy": {
        "user": {
            "displayName": "admin_contoso",
            "email": "admin@contoso.onmicrosoft.com"
        }
    },
    "parentReference": {
        "siteId": "45bb2a3b-0a4e-46f4-8c68-749c3fea75d3"
    },
    "publishingState": {
        "level": "draft",
        "versionId": "0.4"
    },
    "reactions": {}
}
```

### Example 3: Get a page with page content

#### Request

To access the page with page content, append the `?expand=canvasLayout` query string.

```http
GET /sites/{site-id}/pages/{page-id}/microsoft.graph.sitePage?expand=canvasLayout
```

#### Response
```json
{
  "description": "Reiciendis placeat dolores.",
  "eTag": "\"{F45354CB-D634-45DF-8B88-2B4E96A1DC45},8\"",
  "id": "f45354cb-d634-45df-8b88-2b4e96a1dc45",
  "lastModifiedDateTime": "2023-04-16T10:01:41Z",
  "name": "autotest Electronic Convertible.aspx",
  "webUrl": "SitePages/autotest Electronic Convertible.aspx",
  "title": "autotest Electronic Convertible",
  "pageLayout": "article",
  "thumbnailWebUrl": "https://media.akamai.odsp.cdn.office.net/sitepagethumbnail.png",
  "promotionKind": "page",
  "showComments": false,
  "showRecommendedPages": true,
  "createdBy": {
    "user": {
        "displayName": "Rahul Mittal",
        "email": "rahmit@contoso.com"
    }
  },
  "lastModifiedBy": {
    "user": {
        "displayName": "Rahul Mittal",
        "email": "rahmit@contoso.com"
    }
  },
  "parentReference": {
    "listId": "468fc883-e278-4773-ba09-91351a1e42ed",
    "siteId": "45bb2a3b-0a4e-46f4-8c68-749c3fea75d3"
  },
  "contentType": {
    "id": "0x0101009D1CB255DA76424F860D91F20E6C4118009E6554A5E299E84FB2E07731DD6C6D4A",
    "name": "Site Page"
  },
  "publishingState": {
    "level": "draft",
    "versionId": "0.4"
  },
  "reactions": {},
  "canvasLayout": {
    "horizontalSections": [
      {
        "layout": "threeColumns",
        "id": "1",
        "emphasis": "neutral",
        "columns": [
          {
            "id": "1",
            "width": 4,
            "webparts": [
              {
                "@odata.type": "#oneDrive.textWebPart",
                "id": "f6d0ef70-c977-45e4-ae4b-4676a30d5aab",
                "innerHtml": "<h1>sample content</h1>"
              }
            ]
          },
          {
            "id": "2",
            "width": 4,
            "webparts": [
              {
                "@odata.type": "#oneDrive.textWebPart",
                "id": "99f59f91-c853-433e-9e75-ad7a32e46106",
                "innerHtml": "<h1>sample content</h1>"
              }
            ]
          },
          {
            "id": "3",
            "width": 4,
            "webparts": [
              {
                "@odata.type": "#oneDrive.textWebPart",
                "id": "48998492-9633-48b8-a7e9-d293533b4fa6",
                "innerHtml": "<h1>sample content</h1>"
              }
            ]
          }
        ]
      }
    ]
  }
}
```

<!--
{
  "type": "#page.annotation",
  "description": "Get a page in a site",
  "keywords": "",
  "section": "documentation",
  "tocPath": "Pages/Get",
  "suppressions": [
  ]
}
-->
