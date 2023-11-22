---
title: "serviceUpdateMessage resource type"
description: "Represents the announcements of changes in a service."
author: "payiAzure"
ms.localizationpriority: medium
ms.prod: "service-communications"
doc_type: resourcePageType
---

# serviceUpdateMessage resource type

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents the announcements about changes in a service.

Represents announcements such as major updates, new features in a product; for example, the publication of a new SharePoint feature.

Inherits from [serviceAnnouncementBase](../resources/serviceannouncementbase.md).

## Methods
|Method|Return type|Description|
|:---|:---|:---|
|[Get serviceUpdateMessage](../api/serviceupdatemessage-get.md)|[serviceUpdateMessage](../resources/serviceupdatemessage.md)|Retrieve the properties and relationships of a [serviceUpdateMessage](../resources/serviceupdatemessage.md) object. |
|[markRead](../api/serviceupdatemessage-markread.md)|Boolean|Mark a list of [serviceUpdateMessage](../resources/serviceupdatemessage.md)s as **read** for the signed in user.|
|[markUnread](../api/serviceupdatemessage-markunread.md)|Boolean|Mark a list of [serviceUpdateMessage](../resources/serviceupdatemessage.md)s as **unread** for the signed in user.|
|[archive](../api/serviceupdatemessage-archive.md)|Boolean|Archive a list of [serviceUpdateMessage](../resources/serviceupdatemessage.md)s for the signed in user.|
|[unarchive](../api/serviceupdatemessage-unarchive.md)|Boolean|Unarchive a list of [serviceUpdateMessage](../resources/serviceupdatemessage.md)s for the signed in user.|
|[favorite](../api/serviceupdatemessage-favorite.md)|Boolean|Change the status of a list of [serviceUpdateMessage](../resources/serviceupdatemessage.md)s to favorite for the signed in user.|
|[unfavorite](../api/serviceupdatemessage-unfavorite.md)|Boolean|Remove the favorite status of [serviceUpdateMessage](../resources/serviceupdatemessage.md)s for the signed in user.|
|[List attachments](../api/serviceupdatemessage-list-attachments.md)|[serviceAnnouncementAttachment](../resources/serviceannouncementattachment.md) collection|Get a list of attachments associated with a service message.|

## Properties
|Property|Type|Description|
|:---|:---|:---|
|actionRequiredByDateTime|DateTimeOffset|The expected deadline of the action for the message.|
|attachmentsArchive|Stream|The zip file of all attachments for a message.|
|body|[itemBody](../resources/itembody.md)|The content type and content of the service message body. The supported value for the contentType property is `html`.|
|category|serviceUpdateCategory|The service message category. Possible values are: `preventOrFixIssue`, `planForChange`, `stayInformed`, `unknownFutureValue`.|
|details|Collection([keyValuePair](../resources/keyvaluepair.md))|Additional details about service message. This property doesn't support filters. Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md).|
|endDateTime|DateTimeOffset|The end time of the service message. Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md).|
|hasAttachments|Boolean|Indicates whether the message has any attachment.|
|id|String|The id of the service message. Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md).|
|isMajorChange|Boolean|Indicates whether the message describes a major update for the service.|
|lastModifiedDateTime|DateTimeOffset|The last modified time of the service message. Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md).|
|services|Collection(string)|The affected services by the service message.|
|severity|serviceUpdateSeverity|The severity of the service message. Possible values are: `normal`, `high`, `critical`, `unknownFutureValue`.|
|startDateTime|DateTimeOffset|The start time of the service message. Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md).|
|tags|Collection(string)|A collection of tags for the service message. Tags are provided by the service team/support team who post the message to tell whether this message contains privacy data, or whether this message is for a service new feature update, and so on.|
|title|String|The title of the service message. Inherited from [serviceAnnouncementBase](../resources/serviceannouncementbase.md).|
|viewPoint|[serviceUpdateMessageViewpoint](../resources/serviceupdatemessageviewpoint.md)|Represents user viewpoints data of the service message. This data includes message status such as whether the user has archived, read, or marked the message as favorite. This property is null when accessed with application permissions.|

## Relationships
|Relationship|Type|Description|
|:---|:---|:---|
|attachments|Collection([serviceAnnouncementAttachment](../resources/serviceannouncementattachment.md))|A collection of [serviceAnnouncementAttachments](../resources/serviceannouncementattachment.md).|

## JSON representation
The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "keyProperty": "id",
  "@odata.type": "microsoft.graph.serviceUpdateMessage",
  "baseType": "microsoft.graph.serviceAnnouncementBase",
  "openType": false
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.serviceUpdateMessage",
  "startDateTime": "String (timestamp)",
  "endDateTime": "String (timestamp)",
  "lastModifiedDateTime": "String (timestamp)",
  "title": "String",
  "details": [
    {
      "@odata.type": "microsoft.graph.keyValuePair"
    }
  ],
  "id": "String (identifier)",
  "body": {
    "@odata.type": "microsoft.graph.itemBody"
  },
  "category": "String",
  "severity": "String",
  "tags": [
    "String"
  ],
  "isMajorChange": "Boolean",
  "actionRequiredByDateTime": "String (timestamp)",
  "services": [
    "String"
  ],
  "viewPoint": {
    "@odata.type": "microsoft.graph.serviceUpdateMessageViewpoint"
  },
  "hasAttachments": "Boolean",
  "attachmentsArchive": "Stream"
}
```

