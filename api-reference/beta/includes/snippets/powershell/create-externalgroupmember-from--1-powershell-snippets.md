---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Search

$params = @{
	Id = "e811976d-83df-4cbd-8b9b-5215b18aa874"
	Type = "user"
}

New-MgExternalConnectionGroupMember -ExternalConnectionId $externalConnectionId -ExternalGroupId $externalGroupId -BodyParameter $params

```