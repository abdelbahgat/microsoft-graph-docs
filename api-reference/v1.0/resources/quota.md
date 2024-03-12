---
author: JeremyKelley
title: quota
ms.localizationpriority: medium
description: "The quota resource provides details about space constraints on a drive resource."
ms.prod: files
doc_type: resourcePageType
---

# quota resource type

Namespace: microsoft.graph

The **quota** resource provides details about space constraints on a [drive](drive.md) resource. In OneDrive Personal, the values reflect the total/used unified storage quota across multiple Microsoft services.

## JSON representation

Here is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [ ],
  "@odata.type": "microsoft.graph.quota"
}-->

```json
{
  "deleted": 1024,
  "remaining": 1024,
  "state": "normal | nearing | critical | exceeded",
  "storagePlanInformation": {
    "upgradeAvailable": true
  },
  "total": 1024,
  "used": 1024
}
```

## Properties

| Property name | Type   | Description                                                                 |
|:--------------|:-------|:----------------------------------------------------------------------------|
| deleted       | Int64  | Total space consumed by files in the recycle bin, in bytes. Read-only.      |
| remaining     | Int64  | Total space remaining before reaching the quota limit, in bytes. Read-only. |
| state         | string | Enumeration value that indicates the state of the storage space. Read-only. |
| storagePlanInformation  | [storagePlanInformation](storageplaninformation.md) | Information about the drive's storage quota plans. Only in Personal OneDrive.|
| total         | Int64  | Total allowed storage space, in bytes. Read-only.                           |
| used          | Int64  | Total space used, in bytes. Read-only.                                      |


## State Enumeration

| Value      | Description                                                                                                                                                                 |
|:-----------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| `normal`   | The drive has plenty of remaining quota left.                                                                                                                               |
| `nearing`  | Remaining quota is less than 10% of total quota space.                                                                                                                      |
| `critical` | Remaining quota is less than 1% of total quota space.                                                                                                                       |
| `exceeded` | The used quota has exceeded the total quota. New files or folders cannot be added to the drive until it is under the total quota amount or more storage space is purchased. |

<!-- {
  "type": "#page.annotation",
  "description": "The quota facet provides information about how much space the OneDrive has available.",
  "keywords": "quota,available,remaining,used",
  "section": "documentation",
  "suppressions": [
    "Warning: /api-reference/v1.0/resources/quota.md:
      Found potential enums in resource example that weren't defined in a table:(normal, nearing,critical,exceeded) are in resource, but () are in table"
  ],
  "tocPath": "Facets/Quota"
} -->

