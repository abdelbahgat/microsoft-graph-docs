---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement

$params = @{
	"@odata.type" = "#microsoft.graph.windows10TeamGeneralConfiguration"
	description = "Description value"
	displayName = "Display Name value"
	version = 7
	azureOperationalInsightsBlockTelemetry = $true
	azureOperationalInsightsWorkspaceId = "Azure Operational Insights Workspace Id value"
	azureOperationalInsightsWorkspaceKey = "Azure Operational Insights Workspace Key value"
	connectAppBlockAutoLaunch = $true
	maintenanceWindowBlocked = $true
	maintenanceWindowDurationInHours = 
	maintenanceWindowStartTime = "11:59:09.3130000"
	miracastChannel = "one"
	miracastBlocked = $true
	miracastRequirePin = $true
	settingsBlockMyMeetingsAndFiles = $true
	settingsBlockSessionResume = $true
	settingsBlockSigninSuggestions = $true
	settingsDefaultVolume = 
	settingsScreenTimeoutInMinutes = 
	settingsSessionTimeoutInMinutes = 
	settingsSleepTimeoutInMinutes = 
	welcomeScreenBlockAutomaticWakeUp = $true
	welcomeScreenBackgroundImageUrl = "https://example.com/welcomeScreenBackgroundImageUrl/"
	welcomeScreenMeetingInformation = "showOrganizerAndTimeOnly"
}

New-MgDeviceManagementDeviceConfiguration -BodyParameter $params

```