---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.Governance

$params = @{
	id = "4540a08f-8ab5-43f6-a923-015275799197"
	displayName = "policy with custom access package workflow extension"
	description = "Run specified custom access package workflow extension at different stages."
	accessPackageId = "ba5807c7-2aa9-4c8a-907e-4a17ee587500"
	requestApprovalSettings = $null
	requestorSettings = @{
		acceptRequests = $true
		scopeType = "AllExistingDirectorySubjects"
		allowedRequestors = @(
		)
	}
	accessReviewSettings = $null
	customExtensionHandlers = @(
	)
}

Set-MgEntitlementManagementAccessPackageAssignmentPolicy -AccessPackageAssignmentPolicyId $accessPackageAssignmentPolicyId -BodyParameter $params

```