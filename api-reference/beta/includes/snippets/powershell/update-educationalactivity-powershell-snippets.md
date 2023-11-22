---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.People

$params = @{
	institution = @{
		location = @{
			type = "business"
			postOfficeBox = $null
			street = "12000 E Prospect Rd"
			city = "Fort Collins"
			state = "Colorado"
			countryOrRegion = "USA"
			postalCode = "80525"
		}
	}
}

# A UPN can also be used as -UserId.
Update-MgBetaUserProfileEducationalActivity -UserId $userId -EducationalActivityId $educationalActivityId -BodyParameter $params

```