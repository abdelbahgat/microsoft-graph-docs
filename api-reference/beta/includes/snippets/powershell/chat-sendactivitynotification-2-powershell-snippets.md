---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Teams

$params = @{
	topic = @{
		source = "entityUrl"
		value = "https://graph.microsoft.com/beta/chats/{chatId}/messages/{messageId}"
	}
	activityType = "approvalRequired"
	previewText = @{
		content = "Deployment requires your approval"
	}
	recipient = @{
		"@odata.type" = "microsoft.graph.aadUserNotificationRecipient"
		userId = "569363e2-4e49-4661-87f2-16f245c5d66a"
	}
	templateParameters = @(
		@{
			name = "approvalTaskId"
			value = "2020AAGGTAPP"
		}
	)
}

Send-MgBetaChatActivityNotification -ChatId $chatId -BodyParameter $params

```