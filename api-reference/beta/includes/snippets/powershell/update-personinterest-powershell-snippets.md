---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.People

$params = @{
	Categories = @(
		"Sports"
	)
}

# A UPN can also be used as -UserId.
Update-MgUserProfileInterest -UserId $userId -PersonInterestId $personInterestId -BodyParameter $params

```