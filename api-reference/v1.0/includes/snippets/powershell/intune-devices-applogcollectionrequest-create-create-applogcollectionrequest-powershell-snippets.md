---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement

$params = @{
	"@odata.type" = "#microsoft.graph.appLogCollectionRequest"
	status = "completed"
	errorMessage = "Error Message value"
	customLogFolders = @(
		"Custom Log Folders value"
	)
	completedDateTime = [System.DateTime]::Parse("2016-12-31T23:58:52.3534526-08:00")
}

New-MgDeviceManagementMobileAppTroubleshootingEventAppLogCollectionRequest -MobileAppTroubleshootingEventId $mobileAppTroubleshootingEventId -BodyParameter $params

```