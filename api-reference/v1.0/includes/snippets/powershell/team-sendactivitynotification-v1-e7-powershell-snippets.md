---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Teams

$params = @{
	topic = @{
		source = "entityUrl"
		value = "https://graph.microsoft.com/beta/teams/{teamId}/channels/{channelId}/messages/{messageId}/replies/{replyId}"
	}
	activityType = "reservationStatusUpdated"
	previewText = @{
		content = "You have moved up the queue"
	}
	recipient = @{
		"@odata.type" = "microsoft.graph.aadUserNotificationRecipient"
		userId = "jacob@contoso.com"
	}
	templateParameters = @(
		@{
			name = "reservationId"
			value = "TREEE433"
		}
		@{
			name = "currentSlot"
			value = "23"
		}
	)
}

Send-MgTeamActivityNotification -TeamId $teamId -BodyParameter $params

```