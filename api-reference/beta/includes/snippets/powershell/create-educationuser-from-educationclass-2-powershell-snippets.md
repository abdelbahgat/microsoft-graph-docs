---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Education

$params = @{
	"@odata.id" = "https://graph.microsoft.com/beta/education/users/14011"
}

New-MgEducationClassTeacherByRef -EducationClassId $educationClassId -BodyParameter $params

```