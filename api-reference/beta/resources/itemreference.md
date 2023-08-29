---
author: JeremyKelley
description: "The ItemReference resource provides information necessary to address a DriveItem via the API."
ms.date: 09/10/2017
title: ItemReference
ms.localizationpriority: medium
doc_type: resourcePageType
ms.prod: "sharepoint"
---
# ItemReference resource type

Namespace: microsoft.graph

The **ItemReference** resource provides information necessary to address a [driveItem](driveitem.md) via the API.

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [ "path", "shareId", "sharepointIds" ],
  "@odata.type": "microsoft.graph.itemReference"
}-->

```json
{
  "driveId": "string",
  "driveType": "personal | business | documentLibrary",
  "id": "string",
  "name": "string",
  "path": "string",
  "shareId": "string",
  "sharepointIds": { "@odata.type": "microsoft.graph.sharepointIds" },
  "siteId": "string"
}
```

## Properties

| Property      | Type              | Description
|:--------------|:------------------|:-----------------------------------------
| driveId       | String            | Unique identifier of the drive instance that contains the item. Read-only.
| driveType     | String            | Identifies the type of drive. See [drive][] resource for values.
| id            | String            | Unique identifier of the item in the drive. Read-only.
| name          | String            | The name of the item being referenced. Read-only.
| path          | String            | Path that can be used to navigate to the item. Read-only.
| shareId       | String            | A unique identifier for a shared resource that can be accessed via the [Shares][] API.
| sharepointIds | [sharepointIds][] | Returns identifiers useful for SharePoint REST compatibility. Read-only.
| siteId        | String            | For OneDrive for Business and SharePoint, this property represents the ID of the site that contains the parent document library of the driveItem resource. The value is the same as the id property of that [site][] resource. It is an [opaque string that consists of three identifiers](/graph/api/resources/site?view=graph-rest-beta&preserve-view=true#id-property) of the site. <br>For OneDrive, this property is not populated.

[drive]: ../resources/drive.md
[sharepointIds]: ../resources/sharepointids.md
[Shares]: ../api/shares-get.md
[site]: ../resources/site.md

## Remarks

To address a **driveItem** from an **itemReference** resource, construct a URL of the format:

```http
GET https://graph.microsoft.com/v1.0/drives/{driveId}/items/{id}
```

The **path** value is an API path relative to the target drive, for example: `/drive/root:/Documents/myfile.docx`.

To retrieve the human-readable path for a breadcrumb, you can safely ignore everything up to the first `:` in the path string.

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "ItemReference returns a pointer to another item.",
  "section": "documentation",
  "tocPath": "Resources/ItemReference"
} -->


