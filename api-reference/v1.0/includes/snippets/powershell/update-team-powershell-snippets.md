---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Teams

$params = @{
	MemberSettings = @{
		AllowCreateUpdateChannels = $true
	}
	MessagingSettings = @{
		AllowUserEditMessages = $true
		AllowUserDeleteMessages = $true
	}
	FunSettings = @{
		AllowGiphy = $true
		GiphyContentRating = "strict"
	}
}

Update-MgTeam -TeamId $teamId -BodyParameter $params

```