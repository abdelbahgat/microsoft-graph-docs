---
author: JeremyKelley
title: "site resource type"
description: The site resource provides metadata and relationships for a Sharepoint site. 
ms.localizationpriority: high
ms.prod: "sharepoint"
doc_type: resourcePageType
---

# site resource type

Namespace: microsoft.graph

The **site** resource provides metadata and relationships for a SharePoint site.

## Methods

| Method                | Return type | Description
|:-------------------------|:-------------|:----------
| [Get root site][]        | site | Access the root SharePoint site within a tenant.
| [Get site][]             | site | Access a sharePoint site using the siteId.
| [Get site by path][]     | site | Access the root SharePoint site with a relative path.
| [Get site for a group][] | site | Access the team site for a group.
| [Get analytics][]              | [itemAnalytics][] | Get analytics for this resource. 
| [Get activities by interval][] | [itemActivityStat][] | Get a collection of **itemActivityStats** within the specified time interval.
| [Search for sites][]     | collection of site | Search across a SharePoint tenant for sites that match keywords provided.
| [Follow site][]          | collection of site | Follow a user's site or multiple sites.
| [Unfollow site][]        | collection of site | Follow a user's site or multiple sites.
| [List followed sites][]  | collection of site | List the sites that have been followed by the signed in user.
| [Get permission][]             | GET /sites/{site-id}/permissions/{permission-id}
| [List permissions][]           | GET /sites/{site-id}/permissions
| [Create permissions][]         | POST /sites/{site-id}/permissions
| [Delete permission][]         | DELETE /sites/{site-id}/permissions/{permission-id}
| [Update permission][]         | PATCH /sites/{site-id}/permissions/{permission-id}
| [List operations](../api/site-list-operations.md)|[richLongRunningOperation](../resources/richlongrunningoperation.md) collection|Get a list of [rich long-running operations](../resources/richlongrunningoperation.md) associated with a [site](../resources/site.md).

[Get site]: ../api/site-get.md
[Get root site]: ../api/site-get.md
[Get site by path]: ../api/site-getbypath.md
[Get site for a group]: ../api/site-get.md
[Get analytics]: ../api/itemanalytics-get.md
[Get activities by interval]: ../api/itemactivitystat-getactivitybyinterval.md
[Search for sites]: ../api/site-search.md
[itemActivityStat]: itemactivitystat.md
[Follow site]: ../api/site-follow.md
[Unfollow site]: ../api/site-unfollow.md
[List followed sites]: ../api/sites-list-followed.md
[Get permission]: ../api/site-get-permission.md
[List permissions]: ../api/site-list-permissions.md
[Create permissions]: ../api/site-post-permissions.md
[Delete permission]: ../api/site-delete-permission.md
[Update permission]: ../api/site-update-permission.md

## Properties

| Property            | Type                                | Description                                                                                    |
| :----------------------- | :---------------------------------- | :--------------------------------------------------------------------------------------------- |
| **id**                   | string                              | The unique identifier of the item. Read-only.                                                  |
| **createdDateTime**      | DateTimeOffset                      | The date and time the item was created. Read-only.                                             |
| **description**          | string                              | The descriptive text for the site.                                                             |
| **displayName**          | string                              | The full title for the site. Read-only.                                                        |
| **eTag**                 | string                              | ETag for the item. Read-only.                                                                  |
| **lastModifiedDateTime** | DateTimeOffset                      | The date and time the item was last modified. Read-only.                                       |
| **name**                 | string                              | The name / title of the item.                                                                  |
| **root**                 | [root](root.md)                     | If present, indicates that this is the root site in the site collection. Read-only.            |
| **sharepointIds**        | [sharepointIds](sharepointids.md)   | Returns identifiers useful for SharePoint REST compatibility. Read-only.                       |
| **siteCollection**       | [siteCollection](sitecollection.md) | Provides details about the site's site collection. Available only on the root site. Read-only. |
| **webUrl**               | string (url)                        | URL that displays the item in the browser. Read-only.                                          |

### id property
A **site** is identified by a unique ID that is a composite of the following values:
* Site collection hostname (contoso.sharepoint.com)
* Site collection unique ID (GUID)
* Site unique ID (GUID)
  
The `root` identifier always references the root site for a given target, as follows:

* `/sites/root`: The tenant root site.
* `/groups/{group-id}/sites/root`: The group's team site.
  
## Relationships

| Relationship      | Type                                             | Description
|:------------------|:-------------------------------------------------|:----------------------
| **analytics**     | [itemAnalytics][] resource                       | Analytics about the view activities that took place in this site.
| **columns**       | Collection([columnDefinition][])                 | The collection of column definitions reusable across lists under this site.
| **contentTypes**  | Collection([contentType][])                      | The collection of content types defined for this site.
| **drive**         | [drive][]                                        | The default drive (document library) for this site.
| **drives**        | Collection([drive][])                            | The collection of drives (document libraries) under this site.
| **items**         | Collection([baseItem][])                         | Used to address any item contained in this site. This collection can't be enumerated.
| **lists**         | Collection([list][])                             | The collection of lists under this site.
| **onenote**       | [onenote][]                                      | Calls the OneNote service for notebook related operations.
| **operations**    | [richLongRunningOperation](../resources/richlongrunningoperation.md) collection | The collection of long-running operations on the site.
| **permissions**   | Collection([permission][])                       | The permissions associated with the site. Nullable.
| **sites**         | Collection([site][])                             | The collection of the sub-sites under this site.
| **termStore**     | [microsoft.graph.termStore.store]                | The default termStore under this site.
| **termStores**    | Collection([microsoft.graph.termStore.store])    | The collection of termStores under this site.

[columnDefinition]: columndefinition.md
[baseItem]: baseitem.md
[contentType]: contenttype.md
[drive]: drive.md
[identitySet]: identityset.md
[itemAnalytics]: itemanalytics.md
[list]: list.md
[permission]: permission.md
[site]: site.md
[onenote]: onenote.md
[microsoft.graph.termStore.store]: termstore-store.md

## JSON representation

The following is a JSON representation of the resource.

The **site** resource is derived from [**baseItem**](baseitem.md) and inherits properties from that resource.

<!--{
  "blockType": "resource",
  "optionalProperties": [
    "root",
    "sharepointIds",
    "siteCollection",
    "drive",
    "drives",
    "permissions",
    "sites"
  ],
  "keyProperty": "id",
  "baseType": "microsoft.graph.baseItem",
  "@odata.type": "microsoft.graph.site"
}-->

```json
{
  "id": "string",
  "root": { "@odata.type": "microsoft.graph.root" },
  "sharepointIds": { "@odata.type": "microsoft.graph.sharepointIds" },
  "siteCollection": {"@odata.type": "microsoft.graph.siteCollection"},
  "displayName": "string",

  /* relationships */
  "analytics": { "@odata.type": "microsoft.graph.itemAnalytics" },
  "contentTypes": [ { "@odata.type": "microsoft.graph.contentType" }],
  "drive": { "@odata.type": "microsoft.graph.drive" },
  "drives": [ { "@odata.type": "microsoft.graph.drive" }],
  "items": [ { "@odata.type": "microsoft.graph.baseItem" }],
  "lists": [ { "@odata.type": "microsoft.graph.list" }],
  "operations": [ { "@odata.type": "microsoft.graph.richLongRunningOperation" }],
  "permissions": [ { "@odata.type": "microsoft.graph.permission" }],
  "sites": [ { "@odata.type": "microsoft.graph.site"} ],
  "columns": [ { "@odata.type": "microsoft.graph.columnDefinition" }],
  "onenote": { "@odata.type": "microsoft.graph.onenote"},
  "termStore": { "@odata.type": "microsoft.graph.termStore.store" },
  "termStores": [ { "@odata.type": "microsoft.graph.termStore.store" } ],

  /* inherited from baseItem */
  "name": "string",
  "createdDateTime": "datetime",
  "description": "string",
  "eTag": "string",
  "lastModifiedDateTime": "datetime",
  "webUrl": "url"
}
```

<!-- {
  "type": "#page.annotation",
  "description": "",
  "keywords": "",
  "section": "documentation",
  "tocPath": "Sites",
  "tocBookmarks": { "Resources/Site": "#" }
} -->
