---
title: "Create virtualAppointment"
description: "Create a new virtualAppointment object."
author: "benmicrosoft"
ms.localizationpriority: medium
ms.prod: "cloud-communications"
doc_type: apiPageType
---

# Create virtualAppointment
Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create a new [virtualAppointment](../resources/virtualappointment.md) object.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)                                            |
|:---------------------------------------|:---------------------------------------------------------------------------------------|
| Delegated (work or school account)     | OnlineMeetings.ReadWrite                                  |
| Delegated (personal Microsoft account) | Not supported.                                                                         |
| Application                            | Not supported.

> [!NOTE]
>Virtual appointment will transition from online meeting permissions to virtual appointment permissions during the preview period. As we get closer to the transition, we'll provide additional details on the updated permission requirements and timeline.

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PUT /onlineMeeting/{onlineMeetingId}/virtualAppointment 
```

## Request headers

|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
In the request body, supply a JSON representation of the [virtualAppointment](../resources/virtualappointment.md) object.

You can specify the following properties when you create a **virtualAppointment**.

|Property|Type|Description|
|:---|:---|:---|
|appointmentClients|[virtualAppointmentUser](../resources/virtualappointmentuser.md) collection|The client information for the virtual appointment, including name, email, and SMS phone number. Optional.|
|appointmentClientJoinWebUrl|String|The join web URL of the virtual appointment for clients with waiting room and browser join. Optional.|
|externalAppointmentId|String|The identifier of the appointment from the scheduling system, associated with the current virtual appointment. Optional.|
|externalAppointmentUrl|String|The URL of the appointment resource from the scheduling system, associated with the current virtual appointment. Optional.|
|settings|[virtualAppointmentSettings](../resources/virtualappointmentsettings.md)|The settings associated with the virtual appointment resource. Optional.|



## Response

If successful, this method returns a `201 Created` response code and a [virtualAppointment](../resources/virtualappointment.md) object in the response body.

## Examples

### Request
The following is an example of a request.
<!-- {
  "blockType": "request",
  "name": "create_virtualappointment_from_"
}
-->
``` http
PUT https://graph.microsoft.com/beta/onlineMeeting/MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZi/virtualAppointment
Content-Type: application/json
Content-length: 379

{
    "@odata.type": "#microsoft.graph.virtualAppointment",
    "settings": {
        "@odata.type": "microsoft.graph.virtualAppointmentSettings",
        "allowClientToJoinUsingBrowser": "true"
    },
    "appointmentClients": [
        {
            "@odata.type": "microsoft.graph.virtualAppointmentUser",
            "emailAddress": "gradya@contoso.com",
            "displayName": "Grady Archie",
            "smsCapablePhoneNumber": "123-456-7890"
        }
    ],
    "externalAppointmentId": "AAMkADKnAAA=",
    "externalAppointmentUrl": "https://anyschedulingsystem.com/api/appointments/MkADKnAAA="
}
```


### Response
The following is an example of the response.
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.virtualAppointment"
}
-->
``` http
HTTP/1.1 201 Created
Content-Type: application/json

{
    "@odata.type": "#microsoft.graph.virtualAppointment",
    "id": "0c7fda79-ff00-f57f-37e3-28183b6d09b5",
    "settings": {
        "@odata.type": "microsoft.graph.virtualAppointmentSettings",
        "allowClientToJoinUsingBrowser": "true"
    },
    "appointmentClients": [
        {
            "@odata.type": "microsoft.graph.virtualAppointmentUser",
            "emailAddress": "gradya@contoso.com",
            "displayName": "Grady Archie",
            "smsCapablePhoneNumber": "123-456-7890"
        }
    ],
    "externalAppointmentId": "AAMkADKnAAA=",
    "externalAppointmentUrl": "https://anyschedulingsystem.com/api/appointments/MkADKnAAA=",
    "appointmentClientJoinWebUrl": "https://visit.teams.microsoft.com/webrtc-svc/api/route?tid=a796be92-&convId=19:meeting_=True"
}
```

