---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Teams

$params = @{
	topic = @{
		source = "entityUrl"
		value = "https://graph.microsoft.com/v1.0/teams/{teamId}"
	}
	activityType = "systemDefault"
	previewText = @{
		content = "Take a break"
	}
	recipient = @{
		"@odata.type" = "microsoft.graph.aadUserNotificationRecipient"
		userId = "569363e2-4e49-4661-87f2-16f245c5d66a"
	}
	templateParameters = @(
		@{
			name = "systemDefaultText"
			value = "You need to take a short break"
		}
	)
}

Send-MgTeamActivityNotification -TeamId $teamId -BodyParameter $params

```