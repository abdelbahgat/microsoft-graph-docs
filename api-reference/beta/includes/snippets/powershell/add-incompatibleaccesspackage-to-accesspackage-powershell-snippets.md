---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.Governance

$params = @{
	"@odata.id" = "https://graph.microsoft.com/beta/identityGovernance/entitlementManagement/accessPackages/c0a74b4d-2694-4d5d-a964-1bee4ff0aaf2"
}

New-MgEntitlementManagementAccessPackageIncompatibleAccessPackageByRef -AccessPackageId $accessPackageId -BodyParameter $params

```