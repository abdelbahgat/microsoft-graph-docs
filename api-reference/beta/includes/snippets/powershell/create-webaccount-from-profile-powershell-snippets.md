---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.People

$params = @{
	description = "My Github contributions!"
	userId = "innocenty.popov"
	service = @{
		name = "GitHub"
		webUrl = "https://github.com"
	}
}

# A UPN can also be used as -UserId.
New-MgBetaUserProfileWebAccount -UserId $userId -BodyParameter $params

```