---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.Governance

$params = @{
	displayName = "Last quarter's group reviews April 2021"
	decisions = @(
		"approve"
		"deny"
		"dontKnow"
		"notReviewed"
		"notNotified"
	)
	reviewHistoryPeriodStartDateTime = [System.DateTime]::Parse("2021-01-01T00:00:00Z")
	reviewHistoryPeriodEndDateTime = [System.DateTime]::Parse("2021-04-30T23:59:59Z")
	scopes = @(
		@{
			"@odata.type" = "#microsoft.graph.accessReviewQueryScope"
			queryType = "MicrosoftGraph"
			query = "/identityGovernance/accessReviews/definitions?$filter=contains(scope/query, 'accessPackageAssignments')"
			queryRoot = $null
		}
		@{
			"@odata.type" = "#microsoft.graph.accessReviewQueryScope"
			queryType = "MicrosoftGraph"
			query = "/identityGovernance/accessReviews/definitions?$filter=contains(scope/query, '/groups')"
			queryRoot = $null
		}
	)
}

New-MgIdentityGovernanceAccessReviewHistoryDefinition -BodyParameter $params

```