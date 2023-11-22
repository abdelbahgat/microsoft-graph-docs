---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Beta.DeviceManagement.Actions

$params = @{
	top = 25
	skip = 0
	filter = "(TotalUsageInHour ge 40 and TotalUsageInHour le 80)"
	select = @(
		"CloudPcId"
		"ManagedDeviceName"
		"UserPrincipalName"
		"TotalUsageInHour"
		"DaysSinceLastSignIn"
	)
}

Get-MgBetaDeviceManagementVirtualEndpointReportTotalAggregatedRemoteConnectionReport -BodyParameter $params

```