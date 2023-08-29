---
title: "educationResource resource type"
description: "A base class for all resource objects in the system."
ms.localizationpriority: medium
author: "mmast-msft"
ms.prod: "education"
doc_type: resourcePageType
---

# educationResource resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

A base class for [educationExcelResource](../resources/educationexcelresource.md), [educationFileResource](../resources/educationfileresource.md), [educationLinkResource](../resources/educationlinkresource.md), [educationPowerPointResource](../resources/educationpowerpointresource.md), [educationWordResource](../resources/educationwordresource.md), [educationMediaResource](../resources/educationmediaresource.md), [educationExternalResource](../resources/educationexternalresource.md) and [educationTeamsAppResource](../resources/educationteamsappresource.md).

An educationResource is associated with an [assignment](educationassignment.md) and/or [submission](educationsubmission.md), which represents the learning object that is being handed out or handed in. You cannot instantiate a resource directly; you must make a subclass that will represent the type of resource being used.

This resource stores the common properties across all resource types.


## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|createdBy|[identitySet](identityset.md)|Who created the resource.|
|createdDateTime|Moment in time when the resource was created.  DateTimeOffset|The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|
|displayName|String|Display name of resource.|
|lastModifiedBy|[identitySet](identityset.md)|Who was the last user to modify the resource.|
|lastModifiedDateTime|DateTimeOffset|Moment in time when the resource was last modified.  The Timestamp type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.educationResource"
}-->

```json
{
  "createdBy": {"@odata.type": "microsoft.graph.identitySet"},
  "createdDateTime": "String (timestamp)",
  "displayName": "String",
  "lastModifiedBy": {"@odata.type": "microsoft.graph.identitySet"},
  "lastModifiedDateTime": "String (timestamp)"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "educationResource resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->


