---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Users

$params = @{
	Name = "Volunteer"
}

# A UPN can also be used as -UserId.
New-MgUserOutlookTaskFolder -UserId $userId -BodyParameter $params

```