---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.Governance

$params = @{
	requestType = "AdminRemove"
	accessPackageAssignment = @{
		id = "a6bb6942-3ae1-4259-9908-0133aaee9377"
	}
}

New-MgBetaEntitlementManagementAccessPackageAssignmentRequest -BodyParameter $params

```