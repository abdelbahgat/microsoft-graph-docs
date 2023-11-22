---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement

$params = @{
	"@odata.type" = "#microsoft.graph.macOSGeneralDeviceConfiguration"
	description = "Description value"
	displayName = "Display Name value"
	version = 7
	compliantAppsList = @(
		@{
			"@odata.type" = "microsoft.graph.appListItem"
			name = "Name value"
			publisher = "Publisher value"
			appStoreUrl = "https://example.com/appStoreUrl/"
			appId = "App Id value"
		}
	)
	compliantAppListType = "appsInListCompliant"
	emailInDomainSuffixes = @(
		"Email In Domain Suffixes value"
	)
	passwordBlockSimple = $true
	passwordExpirationDays = 
	passwordMinimumCharacterSetCount = 
	passwordMinimumLength = 
	passwordMinutesOfInactivityBeforeLock = 
	passwordMinutesOfInactivityBeforeScreenTimeout = 
	passwordPreviousPasswordBlockCount = 
	passwordRequiredType = "alphanumeric"
	passwordRequired = $true
}

Update-MgDeviceManagementDeviceConfiguration -DeviceConfigurationId $deviceConfigurationId -BodyParameter $params

```