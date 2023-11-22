---
title: "expirationPattern resource type"
description: "The expiration pattern in a request schedule can be included in an access package assignment request and is present in an access package assignment."
ms.localizationpriority: medium
author: "markwahl-msft"
ms.prod: "governance"
doc_type: "resourcePageType"
---

# expirationPattern resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

In [Microsoft Entra entitlement management](entitlementmanagement-overview.md), an access package assignment request is created by a user who wants to obtain an access package assignment. This request can include a schedule for when the user would like to have an assignment.  An access package assignment that results from such a request also has a schedule.  The expiration field of a [requestSchedule](requestschedule.md) indicates when the access package assignment should expire.

## Properties

| Property     | Type        | Description |
|:-------------|:------------|:------------|
|endDateTime|DateTimeOffset|Timestamp of date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`.|
|duration|Duration|The requestor's desired duration of access represented in ISO 8601 format for durations. For example, PT3H refers to three hours.  If specified in a request, **endDateTime** should not be present and the **type** property should be set to `afterDuration`.|
|type|expirationPatternType|The requestor's desired expiration pattern type.|

### expirationPatternType values

| Member | Value| Description |
|:---------------|:--------|:----------|
|notSpecified|0|No expiration schedule was specified.|
|noExpiration|1|The requestor did not wish the access to expire.|
|afterDateTime|2|Access will expire after a specified date and time.|
|afterDuration|3|Access will expire after a specified duration relative to access being granted. Required when the **duration** property is specified.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.expirationPattern"
}-->

```json
{
    "endDateTime": "2020-09-10T23:06:53.307Z",
    "type": "afterDateTime"
}
```

<!-- uuid: 16cd6b66-4b1a-43a1-adaf-3a886856ed98
2019-02-04 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "expirationPattern resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->
