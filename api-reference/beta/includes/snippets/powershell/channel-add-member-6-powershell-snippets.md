---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Teams

$params = @{
	"@odata.type" = "#microsoft.graph.aadUserConversationMember"
	Roles = @(
	)
	"User@odata.bind" = "https://graph.microsoft.com/beta/users('jacob@contoso.com')"
}

New-MgTeamChannelMember -TeamId $teamId -ChannelId $channelId -BodyParameter $params

```