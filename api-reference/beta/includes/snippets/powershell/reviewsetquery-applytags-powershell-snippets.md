---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Compliance

$params = @{
	TagsToAdd = @(
		@{
			Id = "b4798d14-748d-468e-a1ec-96a2b1d49677"
		}
	)
}

Add-MgComplianceEdiscoveryCaseReviewSetQueryTag -CaseId $caseId -ReviewSetId $reviewSetId -ReviewSetQueryId $reviewSetQueryId -BodyParameter $params

```