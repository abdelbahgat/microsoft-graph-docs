---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.SignIns

$params = @{
	NewAssignmentOrder = @{
		Order = @(
			"City"
			"extension_GUID_ShoeSize"
		)
	}
}

Set-MgIdentityB2XUserFlowUserAttributeAssignmentOrder -B2xIdentityUserFlowId $b2xIdentityUserFlowId -BodyParameter $params

```