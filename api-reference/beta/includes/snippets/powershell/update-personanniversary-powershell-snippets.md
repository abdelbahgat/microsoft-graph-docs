---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.People

$params = @{
	AllowedAudiences = "contacts"
}

# A UPN can also be used as -UserId.
Update-MgUserProfileAnniversary -UserId $userId -PersonAnnualEventId $personAnnualEventId -BodyParameter $params

```