---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Security

$params = @{
	displayName = "My legalHold with sources"
	description = "Created from Graph API"
	"userSources@odata.bind" = @(
		@{
			"@odata.type" = "microsoft.graph.security.userSource"
			email = "SalesTeam@M365x809305.OnMicrosoft.com"
		}
	)
	"siteSources@odata.bind" = @(
		@{
			"@odata.type" = "microsoft.graph.security.siteSource"
		}
	)
}

New-MgBetaSecurityCaseEdiscoveryCaseLegalHold -EdiscoveryCaseId $ediscoveryCaseId -BodyParameter $params

```