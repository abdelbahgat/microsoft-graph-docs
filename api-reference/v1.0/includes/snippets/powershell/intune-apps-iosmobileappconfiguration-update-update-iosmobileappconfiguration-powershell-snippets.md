---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Devices.CorporateManagement

$params = @{
	"@odata.type" = "#microsoft.graph.iosMobileAppConfiguration"
	targetedMobileApps = @(
		"Targeted Mobile Apps value"
	)
	description = "Description value"
	displayName = "Display Name value"
	version = 7
	encodedSettingXml = "ZW5jb2RlZFNldHRpbmdYbWw="
	settings = @(
		@{
			"@odata.type" = "microsoft.graph.appConfigurationSettingItem"
			appConfigKey = "App Config Key value"
			appConfigKeyType = "integerType"
			appConfigKeyValue = "App Config Key Value value"
		}
	)
}

Update-MgDeviceAppManagementMobileAppConfiguration -ManagedDeviceMobileAppConfigurationId $managedDeviceMobileAppConfigurationId -BodyParameter $params

```