---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.DirectoryManagement

$params = @{
	postponeUntilDateTime = [System.DateTime]::Parse("2023-03-01T09:40:39.0420371Z")
}

Invoke-MgBetaPostponeDirectoryRecommendationImpactedResource -RecommendationId $recommendationId -ImpactedResourceId $impactedResourceId -BodyParameter $params

```