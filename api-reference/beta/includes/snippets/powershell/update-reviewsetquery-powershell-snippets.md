---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Compliance

$params = @{
	DisplayName = "My Query 1 - Renamed"
}

Update-MgComplianceEdiscoveryCaseReviewSetQuery -CaseId $caseId -ReviewSetId $reviewSetId -ReviewSetQueryId $reviewSetQueryId -BodyParameter $params

```