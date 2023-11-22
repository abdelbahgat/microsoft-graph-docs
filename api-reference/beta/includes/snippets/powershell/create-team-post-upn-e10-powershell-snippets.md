---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Teams

$params = @{
	"template@odata.bind" = "https://graph.microsoft.com/beta/teamsTemplates('standard')"
	displayName = "My Sample Team"
	description = "My Sample Team’s Description"
	members = @(
		@{
			"@odata.type" = "#microsoft.graph.aadUserConversationMember"
			roles = @(
				"owner"
			)
			"user@odata.bind" = "https://graph.microsoft.com/beta/users('jacob@contoso.com')"
		}
	)
}

New-MgBetaTeam -BodyParameter $params

```