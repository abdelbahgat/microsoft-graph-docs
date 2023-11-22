---
title: "teamwork: sendActivityNotificationToRecipients"
description:  Send activity feed notifications to multiple users, in bulk.
author: eddie-lee-msft
ms.localizationpriority: medium
ms.prod: microsoft-teams
doc_type: apiPageType

---

# teamwork: sendActivityNotificationToRecipients

Namespace: microsoft.graph

Send activity feed notifications to multiple users, in bulk. 

For more details about sending notifications and the requirements for doing so, see
[sending Teams activity notifications](/graph/teams-send-activityfeednotifications).

[!INCLUDE [national-cloud-support](../../includes/global-us.md)]

## Permissions

Choose the permission or permissions marked as least privileged for this API. Use a higher privileged permission or permissions [only if your app requires it](/graph/permissions-overview#best-practices-for-using-microsoft-graph-permissions). For details about delegated and application permissions, see [Permission types](/graph/permissions-overview#permission-types). To learn more about these permissions, see the [permissions reference](/graph/permissions-reference).

<!-- { "blockType": "permissions", "name": "teamwork_sendactivitynotificationtorecipients" } -->
[!INCLUDE [permissions-table](../includes/permissions/teamwork-sendactivitynotificationtorecipients-permissions.md)]

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->

``` http
POST /teamwork/sendActivityNotificationToRecipients
```

## Request headers

| Name          | Description                 |
| :------------ | :-------------------------- |
| Authorization | Bearer {token}. Required.   |
| Content-Type  | application/json. Required. |

> **Note**: The token provided must be at least 45 minutes away from expiry. The API call will return a `412 Precondition Failed` response if the token expires within 45 minutes.

## Request body

In the request body, supply a JSON representation of the parameters.

The following table shows the parameters that can be used with this action.

| Parameter          | Type                                                         | Description                                                  |
| :----------------- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| topic              | [teamworkActivityTopic](../resources/teamworkactivitytopic.md) | Topic of the notification. Specifies the resource being talked about. |
| activityType       | String                                                       | Activity type. This must be declared in the [Teams app manifest](/microsoftteams/platform/overview). |
| chainId            | Int64                                                        | Optional. Used to override a previous notification. Use the same `chainId` in subsequent requests to override the previous notification. |
| previewText        | [itemBody](../resources/itembody.md)                         | Preview text for the notification. Microsoft Teams will only show first 150 characters. |
| templateParameters | [keyValuePair](../resources/keyvaluepair.md) collection      | Values for template variables defined in the activity feed entry corresponding to `activityType` in [Teams app manifest](/microsoftteams/platform/overview). |
| teamsAppId         | String                                                       | Optional. Teams app ID of the Teams app associated with the notification. Used to disambiguate installed apps when multiple apps with the same Microsoft Entra app ID are installed for the same recipient user. |
| recipients         | [teamworkNotificationRecipient](../resources/teamworknotificationrecipient.md) collection | Recipients of the notification. Only recipients of type [aadUserNotificationRecipient](../resources/aadusernotificationrecipient.md) are supported. There is an upper limit of 100 recipients in a single request. |

The following resource is supported when setting the `source` value of the **topic** property to `entityUrl`:

- [teamsCatalogApp](../resources/teamscatalogapp.md)

## Response

If successful, this action returns a `202 Accepted` response code.

## Examples

### Example 1: Notify multiple users about pending finance approval requests

The following example shows how to send an activity feed notification to multiple users in bulk. This example notifies multiple stakeholders about pending finance approval requests.

#### Request
# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "teamworksendactivitynotificationtorecipients_v1_e1"
}-->

``` http
POST https://graph.microsoft.com/v1.0/teamwork/sendActivityNotificationToRecipients
Content-Type: application/json

{
    "topic": {
        "source": "entityUrl",
        "value": "https://graph.microsoft.com/v1.0/appCatalogs/teamsApps/{teamsAppId}"
    },
    "activityType": "pendingFinanceApprovalRequests",
    "previewText": {
        "content": "Internal spending team has a pending finance approval requests"
    },
    "recipients": [
    	{
        	"@odata.type": "microsoft.graph.aadUserNotificationRecipient",
        	"userId": "569363e2-4e49-4661-87f2-16f245c5d66a"
    	},
    	{
        	"@odata.type": "microsoft.graph.aadUserNotificationRecipient",
        	"userId": "ab88234e-0874-477c-9638-d144296ed04f"
    	},
    	{
        	"@odata.type": "microsoft.graph.aadUserNotificationRecipient",
        	"userId": "01c64f53-69aa-42c7-9b7f-9f75195d6bfc"
    	}
    ],
    "templateParameters": [
        {
            "name": "pendingRequestCount",
            "value": "5"
        }
    ] 
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/teamworksendactivitynotificationtorecipients-v1-e1-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/teamworksendactivitynotificationtorecipients-v1-e1-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/teamworksendactivitynotificationtorecipients-v1-e1-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/teamworksendactivitynotificationtorecipients-v1-e1-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/teamworksendactivitynotificationtorecipients-v1-e1-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/teamworksendactivitynotificationtorecipients-v1-e1-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/teamworksendactivitynotificationtorecipients-v1-e1-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/teamworksendactivitynotificationtorecipients-v1-e1-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

---


#### Response

<!-- {
  "blockType": "response",
  "truncated": false
}
-->

``` http
HTTP/1.1 202 Accepted
```

### Example 2: Notify multiple users about an event using a custom topic

If you want to link an aspect that is not represented by Microsoft Graph, or you want to customize the name, you can set the source of the `topic` to `text` and pass in a custom value for it. **webUrl** is required when using `topic` source as `text`.

#### Request

# [HTTP](#tab/http)
<!-- {
  "blockType": "request",
  "name": "teamworksendactivitynotificationtorecipients_notifymultipleusers_v1_e2"
}-->

``` http
POST https://graph.microsoft.com/v1.0/teamwork/sendActivityNotificationToRecipients
Content-Type: application/json

{
    "topic": {
        "source": "text",
        "value": "Deployment Approvals Channel",
        "webUrl": "https://teams.microsoft.com/l/message/19:448cfd2ac2a7490a9084a9ed14cttr78c@thread.skype/1605223780000?tenantId=c8b1bf45-3834-4ecf-971a-b4c755ee677d&groupId=d4c2a937-f097-435a-bc91-5c1683ca7245&parentMessageId=1605223771864&teamName=Approvals&channelName=Azure%20DevOps&createdTime=1605223780000"
    },
    "activityType": "deploymentApprovalRequired",
    "previewText": {
        "content": "New deployment requires your approval"
    },
    "templateParameters": [
        {
            "name": "deploymentId",
            "value": "6788662"
        }
    ],
    "recipients": [
    	{
        	"@odata.type": "microsoft.graph.aadUserNotificationRecipient",
        	"userId": "569363e2-4e49-4661-87f2-16f245c5d66a"
    	},
    	{
        	"@odata.type": "microsoft.graph.aadUserNotificationRecipient",
        	"userId": "ab88234e-0874-477c-9638-d144296ed04f"
    	},
    	{
        	"@odata.type": "microsoft.graph.aadUserNotificationRecipient",
        	"userId": "01c64f53-69aa-42c7-9b7f-9f75195d6bfc"
    	}
    ]
}
```

# [C#](#tab/csharp)
[!INCLUDE [sample-code](../includes/snippets/csharp/teamworksendactivitynotificationtorecipients-notifymultipleusers-v1-e2-csharp-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [CLI](#tab/cli)
[!INCLUDE [sample-code](../includes/snippets/cli/teamworksendactivitynotificationtorecipients-notifymultipleusers-v1-e2-cli-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Go](#tab/go)
[!INCLUDE [sample-code](../includes/snippets/go/teamworksendactivitynotificationtorecipients-notifymultipleusers-v1-e2-go-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Java](#tab/java)
[!INCLUDE [sample-code](../includes/snippets/java/teamworksendactivitynotificationtorecipients-notifymultipleusers-v1-e2-java-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [JavaScript](#tab/javascript)
[!INCLUDE [sample-code](../includes/snippets/javascript/teamworksendactivitynotificationtorecipients-notifymultipleusers-v1-e2-javascript-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PHP](#tab/php)
[!INCLUDE [sample-code](../includes/snippets/php/teamworksendactivitynotificationtorecipients-notifymultipleusers-v1-e2-php-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [PowerShell](#tab/powershell)
[!INCLUDE [sample-code](../includes/snippets/powershell/teamworksendactivitynotificationtorecipients-notifymultipleusers-v1-e2-powershell-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

# [Python](#tab/python)
[!INCLUDE [sample-code](../includes/snippets/python/teamworksendactivitynotificationtorecipients-notifymultipleusers-v1-e2-python-snippets.md)]
[!INCLUDE [sdk-documentation](../includes/snippets/snippets-sdk-documentation-link.md)]

---

---


#### Response

<!-- {
  "blockType": "response",
  "truncated": false
}
-->


``` http
HTTP/1.1 202 Accepted
```
