---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Education

$params = @{
	"@odata.id" = "https://graph.microsoft.com/v1.0/education/users/14008"
}

New-MgEducationSchoolUserByRef -EducationSchoolId $educationSchoolId -BodyParameter $params

```