---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Applications

$params = @{
	PermissionId = "e1fe6dd8-ba31-4d61-89e7-88639da4683d"
	PermissionName = "User.Read"
	Classification = "low"
}

New-MgServicePrincipalDelegatedPermissionClassification -ServicePrincipalId $servicePrincipalId -BodyParameter $params

```