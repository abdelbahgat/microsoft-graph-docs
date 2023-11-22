---
title: "recentNotebook resource type"
description: "A recently accessed OneNote notebook. A **recentNotebook** is similar to a notebook but has fewer properties."
ms.localizationpriority: medium
author: "jewan-microsoft"
ms.prod: notes
doc_type: resourcePageType
---

# recentNotebook resource type

Namespace: microsoft.graph

A recently accessed OneNote notebook. A **recentNotebook** is similar to a [notebook](notebook.md) but has fewer properties.

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|displayName|String|The name of the notebook.|
|lastAccessedTime|DateTimeOffset|The date and time when the notebook was last modified. The timestamp represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only.|
|links|[recentNotebookLinks](recentnotebooklinks.md)|Links for opening the notebook. The `oneNoteClientURL` link opens the notebook in the OneNote client, if it's installed. The `oneNoteWebURL` link opens the notebook in OneNote on the web.|
|sourceService|onenoteSourceService|The backend store where the Notebook resides, either `OneDriveForBusiness` or `OneDrive`.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.recentNotebook"
}-->

```json
{
  "displayName": "String",
  "lastAccessedTime": "String (timestamp)",
  "links": {"@odata.type": "microsoft.graph.recentNotebookLinks"},
  "sourceService": "String"
}
```

## Methods

| Method		   | Return Type	|Description|
|:---------------|:--------|:----------|
|[getRecentNotebooks](../api/notebook-getrecentnotebooks.md) | [notebook](notebook.md) collection | Get a collection of the most recently accessed notebooks for the user. |

