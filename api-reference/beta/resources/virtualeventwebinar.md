---
title: "virtualEventWebinar resource type"
description: "Contains information about a virtual event webinar."
author: "awang119"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: resourcePageType
---

# virtualEventWebinar resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Contains information about a virtual event webinar.

Inherits from [virtualEvent](../resources/virtualevent.md).

## Methods

| Method | Return Type |Description |
| ------ | ----------- | ---------- |
| [Get virtualEventWebinar](../api/virtualeventwebinar-get.md) | [virtualEventWebinar](../resources/virtualeventwebinar.md) | Read the properties and relationships of a [virtualEventWebinar](../resources/virtualeventwebinar.md) object. |
| [List by user role](../api/virtualeventwebinar-getbyuserrole.md) | [virtualEventWebinar](../resources/virtualeventwebinar.md) collection | Get a **virtualEventWebinar** collection where the signed-in user is either the organizer or a coorganizer. |
| [List by user ID and role](../api/virtualeventwebinar-getbyuseridandrole.md) | [virtualEventWebinar](../resources/virtualeventwebinar.md) collection | Get a **virtualEventWebinar** collection where the specified user is either the organizer or a coorganizer. |


## Properties

| Property | Type | Description |
| -------- | ---- | ----------- |
| audience | [meetingAudience](#meetingaudience-values) | To whom the webinar is visible. |
| coOrganizers  | [communicationsUserIdentity](communicationsuseridentity.md) collection | Identity information of coorganizers of the webinar. |
| createdBy | [communicationsIdentitySet](communicationsidentityset.md) | Identity information of who created the webinar. Inherited from [virtualEvent](../resources/virtualevent.md). |
| description | String | Description of the webinar. Inherited from [virtualEvent](../resources/virtualevent.md). |
| displayName | String | The display name of the webinar. Inherited from [virtualEvent](../resources/virtualevent.md). |
| endDateTime | [dateTimeTimeZone](../resources/datetimetimezone.md) | End time of the webinar. The **timeZone** property _can_ be set to any of the [time zones currently supported by Windows](/windows-hardware/manufacture/desktop/default-time-zones). Inherited from [virtualEvent](../resources/virtualevent.md). |
| startDateTime | [dateTimeTimeZone](../resources/datetimetimezone.md) | Start time of the webinar. The **timeZone** property _can_ be set to any of the [time zones currently supported by Windows](/windows-hardware/manufacture/desktop/default-time-zones). Inherited from [virtualEvent](../resources/virtualevent.md). |
| id | String | Unique identifier of the webinar. Inherited from [entity](../resources/entity.md).|
| status | [virtualEventStatus](#virtualeventstatus-values) | Status of the webinar. |

### meetingAudience values

| Value | Description |
| ----- | ----------- |
| everyone | The webinar is a public webinar. A public webinar is visible to everyone. |
| organization | The webinar is a private webinar. A private webinar is visible only within the same organization as the organizer. |
| unknownFutureValue | Evolvable enumeration sentinel value. Don't use. |

### virtualEventStatus values

| Value | Description |
| ----- | ----------- |
| draft | The webinar is in draft and only visible to the organizer. |
| published | The organizer published the webinar and it's visible to the audience. |
| canceled | The the organizer canceled the webinar. |
| unknownFutureValue | Evolvable enumeration sentinel value. Don't use. |

## Relationships

| Relationship | Type | Description |
| ------------ | ---- | ----------- |
| registrations | [virtualEventRegistration](../resources/virtualeventregistration.md) collection | Registration records of the webinar. |
| sessions | [virtualEventSession](../resources/virtualeventsession.md)  collection | Sessions of the webinar. Inherited from [virtualEvent](../resources/virtualevent.md). |

## JSON representation

Here's a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.virtualEventWebinar",
  "baseType": "microsoft.graph.virtualEvent",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.virtualEventWebinar",
  "audience": "String",
  "coOrganizers": [{"@odata.type": "microsoft.graph.communicationsUserIdentity"}],
  "createdBy": {"@odata.type": "microsoft.graph.communicationsIdentitySet"},
  "description": "String",
  "displayName": "String",
  "endDateTime": {"@odata.type": "microsoft.graph.dateTimeTimeZone"},
  "id": "String (identifier)",
  "startDateTime": {"@odata.type": "microsoft.graph.dateTimeTimeZone"},
  "status": "String"
}
```
