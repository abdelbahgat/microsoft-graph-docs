---
title: "callTranscript resource type"
description: "Represents a transcript associated with an online meeting."
author: "mankadnandan"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: resourcePageType
---

# callTranscript resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents a transcript associated with an [online meeting](onlinemeeting.md).

## Methods
|  Method       |  Return Type  | Description| 
|:---------------|:--------|:----------|
|[List callTranscripts](../api/onlinemeeting-list-transcripts.md) | [callTranscript](calltranscript.md) collection | Get the list of [callTranscript](../resources/calltranscript.md) objects associated with an [onlineMeeting](../resources/onlinemeeting.md).| 
|[Get callTranscript](../api/calltranscript-get.md) | [callTranscript](calltranscript.md) | Get a [callTranscript](../resources/calltranscript.md) object associated with an [onlineMeeting](../resources/onlinemeeting.md).|
|[delta](../api/calltranscript-delta.md) | [callTranscript](calltranscript.md) collection | Get a set of [callTranscript](../resources/calltranscript.md) resources that have been added for [onlineMeeting](../resources/onlinemeeting.md) instances organized by the specified user.|
|[getAllTranscripts](../api/onlinemeeting-getAllTranscripts.md) | [callTranscript](calltranscript.md) collection | Get the [callTranscript](../resources/calltranscript.md) objects for all the [onlineMeeting](../resources/onlinemeeting.md) instances organized by the specified user.|
 

## Properties

| Property   | Type |Description|
|:---------------|:--------|:----------|
| content| Stream| The content of the transcript. Read-only.|
| createdDateTime| DateTimeOffset|  Date and time at which the transcript was created. The DateTimeOffset type represents date and time information using ISO 8601 format and is always in UTC time. For example, midnight UTC on Jan 1, 2014 is `2014-01-01T00:00:00Z`. Read-only.|
| id| String| The unique identifier for the transcript. Read-only.|
| meetingId | String | The unique identifier of the online meeting related to this transcript. Read-only.|
| meetingOrganizerId| String| The unique identifier of the organizer of the **onlineMeeting** related to this transcript. Read-only.|
| meetingOrganizer| IdentitySet| The identity information of the organizer of the **onlineMeeting** related to this transcript. Read-only.|
| metadataContent| Stream| The time-aligned metadata of the utterances in the transcript. Read-only.|
| transcriptContentUrl| String| The URL which can be used to access the content of the transcript. Read-only.|

## JSON representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.callTranscript"
}-->

```json
{
  "content": "Stream",
  "createdDateTime": "DateTimeOffset",  
  "id": "String (identifier)",
  "meetingId": "String",
  "meetingOrganizerId": "String",
  "meetingOrganizer": "IdentitySet",  
  "metadataContent": "Stream",
  "transcriptContentUrl": "String"
}
```
