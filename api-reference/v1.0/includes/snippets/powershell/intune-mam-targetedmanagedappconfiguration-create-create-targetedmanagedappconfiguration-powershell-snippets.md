---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Devices.CorporateManagement

$params = @{
	"@odata.type" = "#microsoft.graph.targetedManagedAppConfiguration"
	displayName = "Display Name value"
	description = "Description value"
	version = "Version value"
	customSettings = @(
		@{
			"@odata.type" = "microsoft.graph.keyValuePair"
			name = "Name value"
			value = "Value value"
		}
	)
	deployedAppCount = 0
	isAssigned = $true
}

New-MgDeviceAppManagementTargetedManagedAppConfiguration -BodyParameter $params

```