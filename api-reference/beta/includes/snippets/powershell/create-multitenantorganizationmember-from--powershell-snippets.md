---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.SignIns

$params = @{
	tenantId = "4a12efe6-aa14-4d03-8dff-88fc89e2e2ad"
	displayName = "Fabrikam"
}

New-MgBetaTenantRelationshipMultiTenantOrganizationTenant -BodyParameter $params

```