---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.DeviceManagement.Administration

$params = @{
	"@odata.type" = "#microsoft.graph.cloudPcUserSetting"
	displayName = "Example"
	selfServiceEnabled = $true
	restorePointSetting = @{
		frequencyInHours = 16
		userRestoreEnabled = $true
	}
	localAdminEnabled = $false
	resetEnabled = $true
}

Update-MgBetaDeviceManagementVirtualEndpointUserSetting -CloudPcUserSettingId $cloudPcUserSettingId -BodyParameter $params

```