---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Compliance

$params = @{
	DisplayName = "My Reviewset 3"
}

New-MgComplianceEdiscoveryCaseReviewSet -CaseId $caseId -BodyParameter $params

```