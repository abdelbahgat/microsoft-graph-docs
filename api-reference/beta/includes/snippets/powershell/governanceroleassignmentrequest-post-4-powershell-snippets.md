---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Identity.Governance

$params = @{
	roleDefinitionId = "65bb4622-61f5-4f25-9d75-d0e20cf92019"
	resourceId = "e5e7d29d-5465-45ac-885f-4716a5ee74b5"
	subjectId = "74765671-9ca4-40d7-9e36-2f4a570608a6"
	assignmentState = "Eligible"
	type = "AdminRemove"
}

New-MgBetaPrivilegedAccessRoleAssignmentRequest -PrivilegedAccessId $privilegedAccessId -BodyParameter $params

```