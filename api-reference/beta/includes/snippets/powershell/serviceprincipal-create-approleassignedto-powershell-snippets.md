---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Applications

$params = @{
	principalId = "33ad69f9-da99-4bed-acd0-3f24235cb296"
	resourceId = "9028d19c-26a9-4809-8e3f-20ff73e2d75e"
	appRoleId = "ef7437e6-4f94-4a0a-a110-a439eb2aa8f7"
}

New-MgServicePrincipalAppRoleAssignedTo -ServicePrincipalId $servicePrincipalId -BodyParameter $params

```