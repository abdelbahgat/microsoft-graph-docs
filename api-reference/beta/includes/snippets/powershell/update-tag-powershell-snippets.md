---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Compliance

$params = @{
	Description = "This is an updated description."
}

Update-MgComplianceEdiscoveryCaseTag -CaseId $caseId -TagId $tagId -BodyParameter $params

```