---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.SignIns

$params = @{
	"@odata.id" = "https://graph.microsoft.com/odata/groups('dc3d2ce5-7c5e-4dca-a0ef-2145bf6e53ef')"
}

New-MgPolicyMobileDeviceManagementPolicyIncludedGroupByRef -MobilityManagementPolicyId $mobilityManagementPolicyId -BodyParameter $params

```