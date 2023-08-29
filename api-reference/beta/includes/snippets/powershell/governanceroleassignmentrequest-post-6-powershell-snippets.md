---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Identity.Governance

$params = @{
	RoleDefinitionId = "0e88fd18-50f5-4ee1-9104-01c3ed910065"
	ResourceId = "e5e7d29d-5465-45ac-885f-4716a5ee74b5"
	SubjectId = "74765671-9ca4-40d7-9e36-2f4a570608a6"
	AssignmentState = "Eligible"
	Type = "AdminExtend"
	Reason = "extend role assignment"
	Schedule = @{
		Type = "Once"
		StartDateTime = [System.DateTime]::Parse("2018-05-12T23:53:55.327Z")
		EndDateTime = [System.DateTime]::Parse("2018-08-10T23:53:55.327Z")
	}
}

New-MgPrivilegedAccessRoleAssignmentRequest -PrivilegedAccessId $privilegedAccessId -BodyParameter $params

```