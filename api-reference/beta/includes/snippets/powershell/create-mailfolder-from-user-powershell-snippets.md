---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Mail

$params = @{
	DisplayName = "Clutter"
	IsHidden = $true
}

# A UPN can also be used as -UserId.
New-MgUserMailFolder -UserId $userId -BodyParameter $params

```