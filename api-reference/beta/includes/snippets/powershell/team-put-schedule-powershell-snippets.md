---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Teams

$params = @{
	enabled = $true
	timeZone = "America/Chicago"
}

Set-MgBetaTeamSchedule -TeamId $teamId -BodyParameter $params

```