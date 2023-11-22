---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.Users.Actions

$params = @{
	inputIds = @(
		'{rest-formatted-id-1}'
		'{rest-formatted-id-2}'
	)
	sourceIdType = "restId"
	targetIdType = "restImmutableEntryId"
}

# A UPN can also be used as -UserId.
Invoke-MgBetaTranslateUserExchangeId -UserId $userId -BodyParameter $params

```