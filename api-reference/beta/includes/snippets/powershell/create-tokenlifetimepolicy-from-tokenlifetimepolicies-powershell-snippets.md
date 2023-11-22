---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.SignIns

$params = @{
	definition = @(
		'{"TokenLifetimePolicy":{"Version":1,"AccessTokenLifetime":"8:00:00"}}'
	)
	displayName = "Contoso token lifetime policy"
	isOrganizationDefault = $true
}

New-MgBetaPolicyTokenLifetimePolicy -BodyParameter $params

```