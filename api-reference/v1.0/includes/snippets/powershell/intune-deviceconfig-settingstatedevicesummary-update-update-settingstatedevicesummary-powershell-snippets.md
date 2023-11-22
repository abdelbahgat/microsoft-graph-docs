---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement

$params = @{
	"@odata.type" = "#microsoft.graph.settingStateDeviceSummary"
	settingName = "Setting Name value"
	instancePath = "Instance Path value"
	unknownDeviceCount = 2
	notApplicableDeviceCount = 8
	compliantDeviceCount = 4
	remediatedDeviceCount = 5
	nonCompliantDeviceCount = 7
	errorDeviceCount = 0
	conflictDeviceCount = 3
}

Update-MgDeviceManagementDeviceConfigurationDeviceSettingStateSummary -DeviceConfigurationId $deviceConfigurationId -SettingStateDeviceSummaryId $settingStateDeviceSummaryId -BodyParameter $params

```