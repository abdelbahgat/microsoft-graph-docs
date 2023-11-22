---
title: "List recordings"
description: "Get the list of callRecording objects associated with a scheduled onlineMeeting."
author: "v-sdhakshina"
ms.localizationpriority: medium
ms.prod: "microsoft-teams"
doc_type: apiPageType
---

# List recordings

Namespace: microsoft.graph

Get the list of [callRecording](../resources/callrecording.md) objects associated with a scheduled [onlineMeeting](../resources/onlinemeeting.md). This API doesn't support getting call recordings from channel meetings.

> [!NOTE]
> This API works differently in one or more national clouds. For details, see [Microsoft Teams API implementation differences in national clouds](/graph/teamwork-national-cloud-differences).

## Permissions

One of the following permissions is required to call this API. For more information, including how to choose permissions, see [permissions](/graph/permissions-reference).

| Permission type                        | Permissions (from least to most privileged)                        |
|:---------------------------------------|:-------------------------------------------------------------------|
| Delegated (work or school account)     | OnlineMeetingRecording.Read.All                                    |
| Delegated (personal Microsoft account) | Not supported.                                                     |
| Application                            | OnlineMeetingRecording.Read.All, OnlineMeetingRecording.Read.Chat |

> **Note:** The application permission `OnlineMeetingRecording.Read.Chat` uses [resource-specific consent](/microsoftteams/platform/graph-api/rsc/resource-specific-consent).

To use application permission for this API, tenant administrators must create an application access policy and grant it to a user. This authorizes the app configured in the policy to fetch online meetings or online meeting artifacts on behalf of that user (with the user ID specified in the request path). For more information, see [allow applications to access online meetings on behalf of a user](/graph/cloud-communication-online-meeting-application-access-policy).

> [!NOTE]
> This API works only for a meeting that hasn't expired. For more information, see [Limits and specifications for Microsoft Teams](/microsoftteams/limits-specifications-teams#meeting-expiration).

## HTTP request

```http
GET /me/onlineMeetings/{meetingId}/recordings
GET /users/{userId}/onlineMeetings/{meetingId}/recordings
```

## Optional query parameters

This method doesn't support the [OData query parameters](/graph/query-parameters) to customize the response.

## Request headers

| Header       | Value |
|:---------------|:--------|
| Authorization  | Bearer {token}. Required.  |

## Request body

Don't supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and a collection of [callRecording](../resources/callrecording.md) objects in the response body.

## Examples

### Request

The following example shows a request.

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "list_callRecordings",
  "sampleKeys": ["b935e675-5e67-48b9-8d45-249d5f88e964", "MSpiOTM1ZTY3NS01ZTY3LTQ4YjktOGQ0NS0yNDlkNWY4OGU5NjQqMCoqMTk6bWVldGluZ19ZbU0zTnpJNU9USXRZakU0WlMwME1tUTNMVGt6TVRRdFkyWm1PRGRtWmpsaVptRTNAdGhyZWFkLnYy"]
}
-->
``` http
GET  https://graph.microsoft.com/v1.0/users/b935e675-5e67-48b9-8d45-249d5f88e964/onlineMeetings/MSpiOTM1ZTY3NS01ZTY3LTQ4YjktOGQ0NS0yNDlkNWY4OGU5NjQqMCoqMTk6bWVldGluZ19ZbU0zTnpJNU9USXRZakU0WlMwME1tUTNMVGt6TVRRdFkyWm1PRGRtWmpsaVptRTNAdGhyZWFkLnYy/recordings/
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/list-callrecordings-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/list-callrecordings-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/list-callrecordings-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/list-callrecordings-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/list-callrecordings-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/list-callrecordings-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/list-callrecordings-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

### Response

The following example shows the response.

> **Note:** The response object shown here might be shortened for readability.

<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "Collection(microsoft.graph.callRecording)"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.context": "https://graph.microsoft.com/v1.0/$metadata#users('b935e675-5e67-48b9-8d45-249d5f88e964')/onlineMeetings('MSpiOTM1ZTY3NS01ZTY3LTQ4YjktOGQ0NS0yNDlkNWY4OGU5NjQqMCoqMTk6bWVldGluZ19ZbU0zTnpJNU9USXRZakU0WlMwME1tUTNMVGt6TVRRdFkyWm1PRGRtWmpsaVptRTNAdGhyZWFkLnYy')/recordings",
  "@odata.count": 1,
  "value": [
    {
      "id": "7e31db25-bc6e-4fd8-96c7-e01264e9b6fc",
      "meetingId": "MSpiOTM1ZTY3NS01ZTY3LTQ4YjktOGQ0NS0yNDlkNWY4OGU5NjQqMCoqMTk6bWVldGluZ19ZbU0zTnpJNU9USXRZakU0WlMwME1tUTNMVGt6TVRRdFkyWm1PRGRtWmpsaVptRTNAdGhyZWFkLnYy",
      "createdDateTime": "2023-04-10T08:13:17.5990966Z",
      "recordingContentUrl": "https://graph.microsoft.com/v1.0/$metadata#users('b935e675-5e67-48b9-8d45-249d5f88e964')/onlineMeetings('MSpiOTM1ZTY3NS01ZTY3LTQ4YjktOGQ0NS0yNDlkNWY4OGU5NjQqMCoqMTk6bWVldGluZ19ZbU0zTnpJNU9USXRZakU0WlMwME1tUTNMVGt6TVRRdFkyWm1PRGRtWmpsaVptRTNAdGhyZWFkLnYy')/recordings/('7e31db25-bc6e-4fd8-96c7-e01264e9b6fc')/content",
      "meetingOrganizer": {
        "application": null,
        "device": null,
        "user": {
          "@odata.type": "#Microsoft.Teams.GraphSvc.teamworkUserIdentity",
          "id": "b935e675-5e67-48b9-8d45-249d5f88e964",
          "displayName": null,
          "userIdentityType": "aadUser",
          "tenantId": "d6c9ce1e-4f71-8dc3-5b55-6a411ea46324"
        }
      }
    }
  ]
}
```
