---
title: "notificationChannel resource type"
description: "Represents information about the notification channels of an alert rule selected by a user."
author: "zhishending"
ms.localizationpriority: medium
ms.prod: "cloud-pc"
doc_type: resourcePageType
---

# notificationChannel resource type

Namespace: microsoft.graph.deviceManagement

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Represents information about the notification channels of an [alert rule](../resources/devicemanagement-alertrule.md) selected by a user.

[!INCLUDE [monitoring-api-support-solicit](../includes/monitoring-api-support-solicit.md)]

## Properties

|Property|Type|Description|
|:---|:---|:---|
|notificationChannelType|[microsoft.graph.deviceManagement.notificationChannelType](#notificationchanneltype-values)|The type of the notification channel. The possible values are: `portal`, `email`, `phoneCall`, `sms`, `unknownFutureValue`.|
|notificationReceivers|[microsoft.graph.deviceManagement.notificationReceiver](../resources/devicemanagement-notificationreceiver.md) collection|Information about the notification receivers, such as locale and contact information. For example, `en-us` for locale and `serena.davis@contoso.com` for contact information.|

### notificationChannelType values

|Member|Description|
|:---|:---|
|portal|Indicates that the notification message was published via the Microsoft Endpoint Manager admin center.|
|email|Indicates that the notification message was published via email.|
|phoneCall|Indicates that the notification message was published via phone call.|
|sms|Indicates that the notification message was published via SMS.|
|unknownFutureValue|Evolvable enumeration sentinel value. Do not use.|

## Relationships

None.

## JSON representation

The following is a JSON representation of the resource.
<!-- {
  "blockType": "resource",
  "@odata.type": "microsoft.graph.deviceManagement.notificationChannel"
}
-->
``` json
{
  "@odata.type": "#microsoft.graph.deviceManagement.notificationChannel",
  "notificationChannelType": "String",
  "notificationReceivers": [
    {
        "@odata.type": "#microsoft.graph.deviceManagement.notificationReceiver"
    }
  ]
}
```
