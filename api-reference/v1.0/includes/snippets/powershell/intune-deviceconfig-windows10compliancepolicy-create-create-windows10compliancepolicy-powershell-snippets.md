---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement

$params = @{
	"@odata.type" = "#microsoft.graph.windows10CompliancePolicy"
	description = "Description value"
	displayName = "Display Name value"
	version = 7
	passwordRequired = $true
	passwordBlockSimple = $true
	passwordRequiredToUnlockFromIdle = $true
	passwordMinutesOfInactivityBeforeLock = 
	passwordExpirationDays = 
	passwordMinimumLength = 
	passwordMinimumCharacterSetCount = 
	passwordRequiredType = "alphanumeric"
	passwordPreviousPasswordBlockCount = 
	requireHealthyDeviceReport = $true
	osMinimumVersion = "Os Minimum Version value"
	osMaximumVersion = "Os Maximum Version value"
	mobileOsMinimumVersion = "Mobile Os Minimum Version value"
	mobileOsMaximumVersion = "Mobile Os Maximum Version value"
	earlyLaunchAntiMalwareDriverEnabled = $true
	bitLockerEnabled = $true
	secureBootEnabled = $true
	codeIntegrityEnabled = $true
	storageRequireEncryption = $true
}

New-MgDeviceManagementDeviceCompliancePolicy -BodyParameter $params

```