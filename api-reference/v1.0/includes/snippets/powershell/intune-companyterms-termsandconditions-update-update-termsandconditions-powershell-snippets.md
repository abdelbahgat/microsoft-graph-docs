---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement.Administration

$params = @{
	"@odata.type" = "#microsoft.graph.termsAndConditions"
	displayName = "Display Name value"
	description = "Description value"
	title = "Title value"
	bodyText = "Body Text value"
	acceptanceStatement = "Acceptance Statement value"
	version = 7
}

Update-MgDeviceManagementTermAndCondition -TermsAndConditionsId $termsAndConditionsId -BodyParameter $params

```