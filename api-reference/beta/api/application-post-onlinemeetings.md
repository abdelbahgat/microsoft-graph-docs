---
title: "Create onlineMeeting"
description: "Create an online meeting on behalf of a user specified in the request body."
author: "mkhribech"
ms.localizationpriority: high
ms.prod: "cloud-communications"
doc_type: apiPageType
---

# Create onlineMeeting

Namespace: microsoft.graph

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Create an online meeting on behalf of a user.

> [!TIP]
> This API creates a standalone meeting that is not associated with any event on the user's calendar; therefore, meetings created via this API will not show on the user's calendar.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)           |
| :------------------------------------- | :---------------------------------------------------- |
| Delegated (work or school account)     | OnlineMeetings.ReadWrite                              |
| Delegated (personal Microsoft account) | Not supported.                                        |
| Application                            | OnlineMeetings.ReadWrite.All*                         |

To use application permission for this API, tenant administrators must create an [application access policy](/graph/cloud-communication-online-meeting-application-access-policy) and grant it to a user to authorize the app configured in the policy to create online meetings on behalf of that user (with user ID specified in the request path).

## HTTP request

To create an online meeting with delegated (`/me`) and app (`/users/{userId}`) permission:
<!-- { "blockType": "ignored" } -->
```http
POST /me/onlineMeetings
POST /users/{userId}/onlineMeetings
```

> [!NOTE]
>- `userId` is the object ID of a user in [Azure user management portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/UsersManagementMenuBlade). For more details, see [Allow applications to access online meetings on behalf of a user](/graph/cloud-communication-online-meeting-application-access-policy).

## Request headers

| Name            | Description                 |
| :-------------- | :-------------------------- |
| Authorization   | Bearer {token}. Required.   |
| Content-type    | application/json. Required. |
| Accept-Language | Language. Optional.         |

If the request contains an `Accept-Language` HTTP header, the `content` of `joinInformation` will be in the language and locale variant specified in the `Accept-Language` header. The default content will be in English.

## Request body
In the request body, supply a JSON representation of an [onlineMeeting](../resources/onlinemeeting.md) object.

> [!CAUTION]
>
> Assigning the `presenter` or `coorganizer` role to users who are not registered in Azure Active Directory is not currently supported. For details, see [Known issues](/graph/known-issues#presenter-role-cannot-be-assigned-to-non-azure-ad-participants) for more details.

## Response
If successful, this method returns a `201 Created` response code and an [onlineMeeting](../resources/onlinemeeting.md) object in the response body.

## Examples

### Example 1: Create an online meeting with user token

#### Request

The following is an example of a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "create-onlinemeeting-user-token"
}-->
```http
POST https://graph.microsoft.com/beta/me/onlineMeetings
Content-Type: application/json

{
  "startDateTime":"2019-07-12T14:30:34.2444915-07:00",
  "endDateTime":"2019-07-12T15:00:34.2464912-07:00",
  "subject":"User Token Meeting"
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/create-onlinemeeting-user-token-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/create-onlinemeeting-user-token-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/create-onlinemeeting-user-token-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/create-onlinemeeting-user-token-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/create-onlinemeeting-user-token-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/create-onlinemeeting-user-token-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---


#### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.onlineMeeting"
} -->

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.onlineMeeting",
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#users('f46-17cc-42e7-854-f03d6')/onlineMeetings/$entity",
  "audioConferencing": {
    "tollNumber": "+125254478",
    "tollFreeNumber": "+1663588",
    "ConferenceId": "24299",
    "dialinUrl": "https://dialin.teams.microsoft.com/22f12fa0-499f-b8da330?id=24299"
  },
  "chatInfo": {
    "threadId": "19:meeting_M2IzYzczNTItYmY3OC00MDMjNlOTY4MGEz@thread.skype",
    "messageId": "0",
    "replyChainMessageId": "0"
  },
  "creationDateTime": "2019-07-11T02:17:17.6491364Z",
  "startDateTime": "2019-07-11T02:17:17.6491364Z",
  "endDateTime": "2019-07-11T02:47:17.651138Z",
  "id": "MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZiMdFpHRTNaR1F6WGhyZWFkLnYy",
  "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%3ameeting_M2IzYzczNTItYmY3OC00MDl4MGEz%40thread.skype/0?context=%7b%22Tid%22%3a%22bf-8f1-4af-9b-2d7cd011db47%22%2c%22Oid%22%3a%22550fae72-d51-3ec-8c-374f%22%7d",
  "participants": {
    "organizer": {
      "identity": {
        "user": {
          "id": "550fae72-d251-43ec-868c-373734f",
          "tenantId": "72f988bf-86f1-41af-91ab-2d1db47",
          "displayName": "Mario Rogers"
        }
      },
      "role": "presenter",
      "upn": "upn-value"
    }
  },
  "subject": "User Token Meeting",
  "joinMeetingIdSettings": {
    "isPasscodeRequired": false,
    "joinMeetingId": "1234567890",
    "passcode": null
  }
}
```
>**Note:** If 'Accept-Language: ja' is specified to indicate Japanese, for example, the response will include the following.

```json
    "joinInformation": {
        "content": "data%3Atext%2Fhtml%2C%0A++%3Cdiv+style%3D%22width%3A100%25%3Bheight%3A+20px%3B%22%3E%0A%09%09%3Cspan+style%3D%22white-space%3Anowrap%3Bcolor%3Agray%3Bopacity%3A.36%3B%22%3E________________________________________________________________________________%3C%2Fspan%3E%0A%09+%3C%2Fdiv%3E%0A++++%3Cdiv+class%3D%22me-email-text%22+style%3D%22color%3A%23252424%3Bfont-family%3A'Segoe+UI'%2C'Helvetica+Neue'%2CHelvetica%2CArial%2Csans-serif%3B%22%3E%0A+++%3Cdiv+style%3D%22margin-top%3A+24px%3B+margin-bottom%3A+10px%3B%22%3E%0A++++++++%3Ca+class%3D%22me-email-headline%22%0A++++++++++++++style%3D%22font-size%3A+18px%3Bfont-family%3A'Segoe+UI+Semibold'%2C'Segoe+UI'%2C'Helvetica+Neue'%2CHelvetica%2CArial%2Csans-serif%3Btext-decoration%3A+underline%3Bcolor%3A+%236264a7%3B%22%0A++++++++++++++href%3D%22https%3A%2F%2Fteams.microsoft.com%2Fl%2Fmeetup-join%2F19%253ameeting_NDRiZjRiMmUtODI5OC00MzRlLTk1ZWEtMGY1000000000000%2540thread.v2%2F0%3Fcontext%3D%257b%2522Tid%2522%253a%252279a788bf-86f1-41af-91ab-000000000000%2522%252c%2522Oid%2522%253a%2522d4a060b5-a8fc-450c-837b-000000000000%2522%257d%22%0A++++++++++++++target%3D%22_blank%22+rel%3D%22noreferrer+noopener%22%3EMicrosoft+Teams+%E4%BC%9A%E8%AD%B0%E3%81%AB%E5%8F%82%E5%8A%A0%3C%2Fa%3E%0A++++++%3C%2Fdiv%3E%0A%09+%3Cdiv%3E%0A++++%0A++++++%3Cdiv%3E%0A++++++++%3Ca+class%3D%22me-email-link%22+style%3D%22font-size%3A+14px%3Btext-decoration%3A+none%3Bcolor%3A+%236264a7%3B%22%0A++++++++++href%3D%22tel%3A%2B16477490000%2C%2C11160000%26%2335%3B+%22+target%3D%22_blank%22+rel%3D%22noreferrer+noopener%22%3E%2B16477490000%3C%2Fa%3E%0A++++++%3Cspan+style%3D%22font-size%3A+12px%3B%22%3E%26nbsp%3B++(%E6%9C%89%E6%96%99)+%3C%2Fspan%3E%0A++++++%3C%2Fdiv%3E%0A++++%0A++%3C%2Fdiv%3E%0A%0A%09+%0A++++++%3Cdiv+style%3D%22margin-top%3A+10px%3B+margin-bottom%3A+20px%3B%22%3E%0A++++++++%3Cspan+style%3D%22font-size%3A+12px%3B%22%3E%0A++++++++++%E4%BC%9A%E8%AD%B0+ID%3A%0A++++++++%3C%2Fspan%3E%0A++++++%3Cspan+style%3D%22font-size%3A+14px%3B%22%3E%0A++++++++111+000+00%23%0A++++++%3C%2Fspan%3E%0A++++%3C%2Fdiv%3E%0A++++%0A%09+%0A++++++++%3Cdiv+style%3D%22margin-bottom%3A+24px%3B%22%3E%0A++++++++++++++%3Ca+class%3D%22me-email-link%22+style%3D%22font-size%3A+12px%3Btext-decoration%3A+none%3Bcolor%3A+%236264a7%3B%22+target%3D%22_blank%22+href%3D%22https%3A%2F%2Fdialin.teams.microsoft.com%2F8bf6e654-57eb-4b85-aeaf-36c84429b2fe%3Fid%3D11160000%22+rel%3D%22noreferrer+noopener%22%3E%E6%9C%80%E5%AF%84%E3%82%8A%E3%81%AE%E5%9B%BD%E3%81%AE%E9%9B%BB%E8%A9%B1%E7%95%AA%E5%8F%B7%E3%82%92%E6%A4%9C%E7%B4%A2%3C%2Fa%3E%0A+++++++++%7C%0A++++++++++++++%3Ca+class%3D%22me-email-link%22+style%3D%22font-size%3A+12px%3Btext-decoration%3A+none%3Bcolor%3A+%236264a7%3B%22+target%3D%22_blank%22+href%3D%22https%3A%2F%2Fmysettings.lync.com%2Fpstnconferencing%22+rel%3D%22noreferrer+noopener%22%3E%0A++++++++PIN+%E3%82%92%E3%83%AA%E3%82%BB%E3%83%83%E3%83%88%3C%2Fa%3E%0A+++++++++%7C+%3Ca+class%3D%22me-email-link%22+style%3D%22font-size%3A+12px%3Btext-decoration%3A+none%3Bcolor%3A+%236264a7%3B%22+target%3D%22_blank%22+href%3D%22https%3A%2F%2Faka.ms%2FJoinTeamsMeeting%22+rel%3D%22noreferrer+noopener%22%3ETeams+%E3%81%AE%E8%A9%B3%E7%B4%B0%E3%82%92%E8%A1%A8%E7%A4%BA%3C%2Fa%3E%0A+++++%7C+%3Ca+class%3D%22me-email-link%22+style%3D%22font-size%3A+12px%3Btext-decoration%3A+none%3Bcolor%3A+%236264a7%3B%22+target%3D%22_blank%22+href%3D%22https%3A%2F%2Fteams.microsoft.com%2FmeetingOptions%2F%3ForganizerId%3Dd4a060b5-a8fc-450c-837b-000000000000%26tenantId%3D79a788bf-86f1-41af-91ab-000000000000%26threadId%3D19_meeting_NDRiZjRiMmUtODI5OC00MzRlLTk1ZWEtMGY1000000000000%40thread.v2%26messageId%3D0%26language%3Dja%22+rel%3D%22noreferrer+noopener%22%3E%E4%BC%9A%E8%AD%B0%E3%81%AE%E3%82%AA%E3%83%97%E3%82%B7%E3%83%A7%E3%83%B3%3C%2Fa%3E%0A++++%0A++++++++%3C%2Fdiv%3E%0A++++%0A+++++%0A++++++++%3Cdiv+style%3D%22font-size%3A+14px%3B+margin-bottom%3A+4px%3B%22%3E%0A++++++++++++%E3%83%93%E3%83%87%E3%82%AA%E4%BC%9A%E8%AD%B0%E3%83%87%E3%83%90%E3%82%A4%E3%82%B9%E3%81%A7%E5%8F%82%E5%8A%A0%0A++++++++%3C%2Fdiv%3E%0A%0A++++++++%3Cdiv+style%3D%22font-size%3A12px%3B+margin-bottom%3A+4px%3B%22%3E%0A++++++++++++%3Ca+class%3D%22me-email-link%22+style%3D%22text-decoration%3A+none%3Bcolor%3A+%236264a7%3B%22+href%3D%22%22%3E000000000%40t.abcd.vc%3C%2Fa%3E+VTC+%E4%BC%9A%E8%AD%B0+ID%3A+0180300000%0A++++++++%3C%2Fdiv%3E%0A%0A++++++++%3Cdiv+style%3D%22font-size%3A+12px%3B+margin-bottom%3A+20px%3B%22%3E%0A++++++++%3Ca+class%3D%22me-email-link%22+style%3D%22text-decoration%3A+none%3Bcolor%3A+%236264a7%3B%22+href%3D%22https%3A%2F%2Fdialin.abcd.vc%2Fteams%2F%3Fkey%3D000000000%26conf%3D0180308922%22%3E%E4%BB%A3%E6%9B%BF+VTC+%E3%81%AE%E3%83%80%E3%82%A4%E3%83%A4%E3%83%AB%E6%96%B9%E6%B3%95%3C%2Fa%3E%0A++++++++%3C%2Fdiv%3E%0A++++%0A+++++%0A++++++%3Cdiv+style%3D%22font-size%3A+14px%3B+margin-bottom%3A+4px%3B%22%3E%0A++++++++%0A++++++%3C%2Fdiv%3E%0A++++++%3Cdiv+style%3D%22font-size%3A+12px%3B%22%3E%0A++++++%0A++++++%3C%2Fdiv%3E%0A++++%0A+++++%3C%2Fdiv%3E%0A%09+%3Cdiv+style%3D%22width%3A100%25%3Bheight%3A+20px%3B%22%3E%0A%09%09%3Cspan+style%3D%22white-space%3Anowrap%3Bcolor%3Agray%3Bopacity%3A.36%3B%22%3E________________________________________________________________________________%3C%2Fspan%3E%0A++%3C%2Fdiv%3E%22%2C%0A",
        "contentType": "Html"
    }
```


### Example 2: Create an online meeting in a Microsoft Teams channel with a user token

#### Request

The following is an example of a request.

>**Note:** The Object ID of the user token passed should be a member of the channel represented by **threadId** in the payload.

```http
POST https://graph.microsoft.com/beta/me/onlineMeetings
Content-Type: application/json

{
  "startDateTime":"2019-07-12T14:30:34.2444915-07:00",
  "endDateTime":"2019-07-12T15:00:34.2464912-07:00",
  "subject":"User meeting in Microsoft Teams channel.",
  "chatInfo": {
    "threadId":"19%3A3b5239894b776357c1dd79%40thread.skype"
  }
}
```
#### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "example",
  "truncated": true,
  "@odata.type": "microsoft.graph.onlineMeeting"
} -->

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#users('f40f86-17cc-42e7-85f4-f03880d6')/onlineMeetings/$entity",
  "audioConferencing": {
    "tollNumber": "+12534478",
    "tollFreeNumber": "+18660588",
    "ConferenceId": "24229",
    "dialinUrl": "https://dialin.teams.microsoft.com/22f12fa0-49f-45b-bc69-b8a330?id=24229"
  },
  "chatInfo": {
    "threadId": "19%3A3b52398f3c5244b776357c1dd79%40thread.skype",
    "messageId": "1563302249053",
    "replyChainMessageId": null
  },
  "creationDateTime": "2019-07-11T02:17:17.6491364Z",
  "startDateTime": "2019-07-11T02:17:17.6491364Z",
  "endDateTime": "2019-07-11T02:47:17.651138Z",
  "id": "MSpkYzE3Njc0Yy04MWQ5LTRhZGItHRTNaR1F6WGhyZWFkLnYy",
  "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%3ameeting_M2IzYzczNNlOTY4MGEz%40thread.skype/0?context=%7b%22Tid%22%3a%2288bf-86f1-41af-91ab-2011db47%22%2c%22Oid%22%3a%22fae72-d51-43ec-68c-3704f%22%7d",
  "participants": {
    "organizer": {
      "identity": {
        "user": {
          "id": "55ae72-d251-43ec-868c-373704f",
          "tenantId": "72f98f-86f1-41af-91ab-2d7db47",
          "displayName": "Mario Rogers"
        }
      },
      "role": "presenter",
      "upn": "upn-value"
    }
  },
  "subject": "User meeting in Microsoft Teams channel.",
  "joinMeetingIdSettings": {
    "isPasscodeRequired": false,
    "joinMeetingId": "1234567890",
    "passcode": null
  }
}
```

### Example 3: Create a Microsoft Teams live event with a user token

#### Request

The following is an example of a request.

```http
POST https://graph.microsoft.com/beta/me/onlineMeetings
Content-Type: application/json

{
  "subject":"User Token Live Event",
  "startDateTime":"2020-12-02T14:30:34.2444915+00:00",
  "endDateTime":"2020-12-02T15:00:34.2464912+00:00",
  "isBroadcast": true,
  "broadcastSettings": {
    "allowedAudience": "everyone",
    "isRecordingEnabled": true,
    "isAttendeeReportEnabled": true
  }
}
```

#### Response

The following is an example of the response.

> **Note:** The response object shown here has been shortened for readability. All the properties will be returned from an actual call.

```json
{
  "id": "dc17674c-81d9-4adb-bfb2-8fa442e4622_19:meeting_MGQ4MDDYxODYzMmY2@thread.v2",
  "creationDateTime": "2020-12-02T14:30:34.2444915Z",
  "startDateTime": "2020-09-29T22:35:31.389759Z",
  "endDateTime": "2020-12-02T15:00:34.2464912Z",
  "joinWebUrl": "(redacted)",
  "subject": "User Token Live Event",
  "autoAdmittedUsers": "EveryoneInCompany",
  "isEntryExitAnnounced": true,
  "allowedPresenters": "organization",
  "videoTeleconferenceId": "(redacted)",
  "participants": {
    "organizer": {
      "upn": "(redacted)",
      "role": "producer",
      "identity": {
        "user": {
          "id": "dc174c-81d9-4adb-bfb2-8f6a4622",
          "displayName": null,
          "tenantId": "909581-5130-43e9-88f3-fccde38",
          "identityProvider": "AAD"
        }
      }
    },
    "attendees": [
      {
        "upn": "(redacted)",
        "role": "producer",
        "identity": {
          "user": {
            "id": "dc174c-81d9-4adb-bfb2-8442e4622",
            "displayName": null,
            "tenantId": "909581-5130-43e9-88f3-fcb3cde38",
            "identityProvider": "AAD"
          }
        }
      }
    ],
    "producers": [
      {
        "upn": "(redacted)",
        "role": "producer",
        "identity": {
          "user": {
            "id": "d7674c-81d9-4adb-bfb2-8f6a4622",
            "displayName": null,
            "tenantId": "909c81-5130-43e9-88f3-fcbcde38",
            "identityProvider": "AAD"
          }
        }
      }
    ],
    "contributors": []
  },
  "lobbyBypassSettings": {
    "scope": "organization",
    "isDialInBypassEnabled": false
  },
  "isBroadcast": true,
  "broadcastSettings": {
    "allowedAudience": "organization",
    "isRecordingEnabled": true,
    "isAttendeeReportEnabled": true
  },
  "joinMeetingIdSettings": {
    "isPasscodeRequired": false,
    "joinMeetingId": "1234567890",
    "passcode": null
  }
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "Create onlineMeeting",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": [
  ]
}
-->

### Example 4: Create an online meeting that requires a passcode

The following example shows how to add a passcode to a meeting. The passcode is used when you join a meeting with a **joinMeetingId**. For more details, see [joinMeetingIdSettings](../resources/joinmeetingidsettings.md).
#### Request

The following is an example of a request.

>**Note:** The passcode is automatically generated and a custom passcode is not supported.

```http
POST https://graph.microsoft.com/beta/me/onlineMeetings
Content-Type: application/json

{
  "startDateTime":"2019-07-12T14:30:34.2444915-07:00",
  "endDateTime":"2019-07-12T15:00:34.2464912-07:00",
  "subject":"User meeting",
  "joinMeetingIdSettings": {
    "isPasscodeRequired": true
  }
}
```

#### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "example",
  "truncated": true,
  "@odata.type": "microsoft.graph.onlineMeeting"
} -->

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#users('f4086-17cc-42e7-85f4-f03880d6')/onlineMeetings/$entity",
  "audioConferencing": {
    "tollNumber": "+12525478",
    "tollFreeNumber": "+18690588",
    "ConferenceId": "2999",
    "dialinUrl": "https://dialin.teams.microsoft.com/22fa0-499f-435b-bc69-b8dea330?id=2999"
  },
  "chatInfo": {
    "threadId": "19%3A3b523985568b776357c1dd79%40thread.skype",
    "messageId": "15629053",
    "replyChainMessageId": null
  },
  "creationDateTime": "2019-07-11T02:17:17.6491364Z",
  "startDateTime": "2019-07-11T02:17:17.6491364Z",
  "endDateTime": "2019-07-11T02:47:17.651138Z",
  "id": "MSpkYzE3Njc0Yy04MWQ5LTRhFpHRTNaR1F6WGhyZWFkLnYy",
  "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%3ameeting_M2IzYzczNTItYmY3iMjNlOTY4MGEz%40thread.skype/0?context=%7b%22Tid%22%3a%22f8bf-86f1-41af-91ab-2011db47%22%2c%22Oid%22%3a%20fae72-d251-43ec-86c-377304f%22%7d",
  "participants": {
    "organizer": {
      "identity": {
        "user": {
          "id": "5e72-d251-43ec-868c-3732704f",
          "tenantId": "72fbf-86f1-41af-91ab-2d71db47",
          "displayName": "Mario Rogers"
        }
      },
      "role": "presenter",
      "upn": "upn-value"
    }
  },
  "subject": "User meeting",
  "joinMeetingIdSettings": {
    "isPasscodeRequired": true,
    "joinMeetingId": "1234567890",
    "passcode": "123abc"
  }
}
```


### Example 5: Create an online meeting that does not require a passcode

When **isPasscodeRequired** is set to `false` or when **joinMeetingIdSettings** is not specified in the request, the generated online meeting will not have a passcode.
#### Request

The following is an example of a request.

```http
POST https://graph.microsoft.com/beta/me/onlineMeetings
Content-Type: application/json

{
  "startDateTime":"2019-07-12T14:30:34.2444915-07:00",
  "endDateTime":"2019-07-12T15:00:34.2464912-07:00",
  "subject":"User meeting in Microsoft Teams channel.",
  "joinMeetingIdSettings": {
    "isPasscodeRequired": false
  }
}
```

or

```http
POST https://graph.microsoft.com/beta/me/onlineMeetings
Content-Type: application/json

{
  "startDateTime":"2019-07-12T14:30:34.2444915-07:00",
  "endDateTime":"2019-07-12T15:00:34.2464912-07:00",
  "subject":"User meeting in Microsoft Teams channel."
}
```

#### Response

The following is an example of the response.

>**Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "example",
  "truncated": true,
  "@odata.type": "microsoft.graph.onlineMeeting"
} -->

```http
HTTP/1.1 201 Created
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/beta/$metadata#users('f4053f86-17cc-42e7-85f4-f0389ac980d6')/onlineMeetings/$entity",
  "audioConferencing": {
    "tollNumber": "+12525634478",
    "tollFreeNumber": "+18666390588",
    "ConferenceId": "2425999",
    "dialinUrl": "https://dialin.teams.microsoft.com/22f12fa0-499f-435b-bc69-b8de580ba330?id=2425999"
  },
  "chatInfo": {
    "threadId": "19%3A3b52398f3c524556894b776357c1dd79%40thread.skype",
    "messageId": "1563302249053",
    "replyChainMessageId": null
  },
  "creationDateTime": "2019-07-11T02:17:17.6491364Z",
  "startDateTime": "2019-07-11T02:17:17.6491364Z",
  "endDateTime": "2019-07-11T02:47:17.651138Z",
  "id": "MSpkYzE3Njc0Yy04MWQ5LTRhZGItYmZiMi04ZdFpHRTNaR1F6WGhyZWFkLnYy",
  "joinWebUrl": "https://teams.microsoft.com/l/meetup-join/19%3ameeting_M2IzYzczNTItYmY3OC00MDlmLWJjMzUtYmFiMjNlOTY4MGEz%40thread.skype/0?context=%7b%22Tid%22%3a%2272f988bf-86f1-41af-91ab-2d7cd011db47%22%2c%22Oid%22%3a%22550fae72-d251-43ec-868c-373732c2704f%22%7d",
  "participants": {
    "organizer": {
      "identity": {
        "user": {
          "id": "550fae72-d251-43ec-868c-373732c2704f",
          "tenantId": "72f988bf-86f1-41af-91ab-2d7cd011db47",
          "displayName": "Tyler Stein"
        }
      },
      "role": "presenter",
      "upn": "upn-value"
    }
  },
  "subject": "User meeting in Microsoft Teams channel.",
  "joinMeetingIdSettings": {
    "isPasscodeRequired": false,
    "joinMeetingId": "1234567890",
    "passcode": null
  }
}
```
