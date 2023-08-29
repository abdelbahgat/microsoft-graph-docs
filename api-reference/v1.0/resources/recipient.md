---
title: "recipient resource type"
description: "Represents information about a user in the sending or receiving end of an event, message or group post. "
ms.localizationpriority: medium
author: "abheek-das"
ms.prod: mail
doc_type: resourcePageType
---

# recipient resource type

Namespace: microsoft.graph

Represents information about a user in the sending or receiving end of an event, message or group post.

## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|emailAddress|[EmailAddress](emailaddress.md)|The recipient's email address.|

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.recipient"
}-->

```json
{
  "emailAddress": {"@odata.type": "microsoft.graph.emailAddress"}
}

```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "recipient resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

