---
title: "meetingParticipantInfo resource type"
description: "Information about a participant in a meeting."
author: "ananmishr"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: resourcePageType
---

# meetingParticipantInfo resource type

Namespace: microsoft.graph

Information about a participant in a meeting.

## Properties

| Property | Type                          | Description                                                                         |
| :------- | :---------------------------- | :---------------------------------------------------------------------------------- |
| identity | [identitySet](identityset.md) | Identity information of the participant.                                            |
| upn      | String                        | User principal name of the participant.                                             |
| role     | onlineMeetingRole             | Specifies the participant's role in the meeting.  Possible values are `attendee`, `presenter`, `producer`, and `unknownFutureValue`.|

> [!TIP]
>
> To set the  **presenter** role of a meeting attendee when creating or updating an [onlineMeeting](onlinemeeting.md), the value of **allowedPresenters** must also be set to `roleIsPresenter`.

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [

  ],
  "@odata.type": "microsoft.graph.meetingParticipantInfo"
}-->
```json
{
  "identity": {"@odata.type": "#microsoft.graph.identitySet"},
  "upn": "String",
  "role": "String"
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "meetingParticipantInfo resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->

