---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Education

$params = @{
	Description = "History - World History 1"
	DisplayName = "World History Level 1"
}

Update-MgEducationClass -EducationClassId $educationClassId -BodyParameter $params

```