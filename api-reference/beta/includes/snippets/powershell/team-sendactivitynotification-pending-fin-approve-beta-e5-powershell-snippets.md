---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Teams

$params = @{
	topic = @{
		source = "entityUrl"
		value = "https://graph.microsoft.com/beta/teams/e8bece96-d393-4b9b-b8da-69cedef1a7e7"
	}
	activityType = "pendingFinanceApprovalRequests"
	previewText = @{
		content = "Internal spending team has a pending finance approval requests"
	}
	recipient = @{
		"@odata.type" = "microsoft.graph.teamMembersNotificationRecipient"
		teamId = "e8bece96-d393-4b9b-b8da-69cedef1a7e7"
	}
	templateParameters = @(
		@{
			name = "pendingRequestCount"
			value = "5"
		}
	)
}

Send-MgBetaTeamActivityNotification -TeamId $teamId -BodyParameter $params

```