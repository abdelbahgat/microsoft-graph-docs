---
title: "attendeeBase resource type"
description: "The type of attendee."
ms.localizationpriority: medium
author: "iamgirishck"
ms.prod: calendar
doc_type: resourcePageType
---

# attendeeBase resource type

Namespace: microsoft.graph

The type of attendee.

Derived from [recipient](recipient.md).

## JSON representation

Here is a JSON representation of the resource

<!-- {
  "blockType": "resource",
  "baseType": "microsoft.graph.recipient",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.attendeeBase"
}-->

```json
{
  "type": "String",
  "emailAddress": {"@odata.type": "microsoft.graph.emailAddress"}
}

```
## Properties
| Property	   | Type	|Description|
|:---------------|:--------|:----------|
|emailAddress|[emailAddress](emailaddress.md)|Includes the name and SMTP address of the attendee.|
|type|attendeeType| The type of attendee. The possible values are: `required`, `optional`, `resource`. Currently if the attendee is a person, [findMeetingTimes](../api/user-findmeetingtimes.md) always considers the person is of the `Required` type.|

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "attendeeBase resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->

