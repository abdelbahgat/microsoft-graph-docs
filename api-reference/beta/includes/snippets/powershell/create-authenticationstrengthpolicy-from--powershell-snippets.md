---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.SignIns

$params = @{
	"@odata.type" = "#microsoft.graph.authenticationStrengthPolicy"
	displayName = "Contoso authentication level"
	description = "The only authentication level allowed to access our secret apps"
	allowedCombinations = @(
		"password, hardwareOath"
		"password, sms"
	)
}

New-MgBetaPolicyAuthenticationStrengthPolicy -BodyParameter $params

```