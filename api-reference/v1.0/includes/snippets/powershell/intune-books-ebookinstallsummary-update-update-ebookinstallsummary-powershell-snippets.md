---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Devices.CorporateManagement

$params = @{
	"@odata.type" = "#microsoft.graph.eBookInstallSummary"
	installedDeviceCount = 4
	failedDeviceCount = 1
	notInstalledDeviceCount = 7
	installedUserCount = 2
	failedUserCount = 15
	notInstalledUserCount = 5
}

Update-MgDeviceAppManagementManagedEBookInstallSummary -ManagedEBookId $managedEBookId -BodyParameter $params

```