---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.Governance

$params = @{
	displayName = "Connected organization new name"
	description = "Connected organization new description"
	state = "configured"
}

Update-MgBetaEntitlementManagementConnectedOrganization -ConnectedOrganizationId $connectedOrganizationId -BodyParameter $params

```