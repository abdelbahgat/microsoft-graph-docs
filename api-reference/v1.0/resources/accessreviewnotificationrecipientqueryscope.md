---
title: "accessReviewnotificationrecipientqueryscope resource type"
description: "Specifies a list of users who will receive notifications for access reviews."
author: "zhusijia26"
ms.localizationpriority: medium
ms.prod: "governance"
doc_type: resourcePageType
---

# accessReviewnotificationrecipientqueryscope resource type

Namespace: microsoft.graph

Specifies a static list of recipients (for example, specific users, group owners, or group members) to receive access review notifications.

Inherits from [accessReviewNotificationRecipientScope](../resources/accessreviewnotificationrecipientscope.md).

## Properties
| Property | Type | Description |
| :-------------------------| :---------- | :---------- |
| query | String | Represents the query for who the recipients are. For example, `/groups/{group id}/members` for group members and `/users/{user id}` for a specific user. |
| queryType | String | Indicates the type of query. Allowed value is `MicrosoftGraph`. |
| queryRoot | String | In the scenario where reviewers need to be specified dynamically, indicates the relative source of the query. This property is only required if a relative query (that is, `./manager`) is specified. |


## Relationships
None.

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.accessReviewNotificationRecipientQueryScope"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.accessReviewNotificationRecipientQueryScope",
  "query": "String",
  "queryType": "String",
  "queryRoot": "String"
}
```
