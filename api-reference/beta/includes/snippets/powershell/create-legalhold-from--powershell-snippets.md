---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Compliance

$params = @{
	"@odata.type" = "#microsoft.graph.ediscovery.legalHold"
	description = "String"
	createdBy = @{
		"@odata.type" = "microsoft.graph.identitySet"
	}
	isEnabled = "Boolean"
	status = "String"
	contentQuery = "String"
	errors = @(
		"String"
	)
	displayName = "String"
}

New-MgBetaComplianceEdiscoveryCaseLegalHold -CaseId $caseId -BodyParameter $params

```