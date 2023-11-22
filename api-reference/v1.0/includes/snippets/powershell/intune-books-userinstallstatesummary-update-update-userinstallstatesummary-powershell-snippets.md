---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.Devices.CorporateManagement

$params = @{
	"@odata.type" = "#microsoft.graph.userInstallStateSummary"
	userName = "User Name value"
	installedDeviceCount = 4
	failedDeviceCount = 1
	notInstalledDeviceCount = 7
}

Update-MgDeviceAppManagementManagedEBookUserStateSummary -ManagedEBookId $managedEBookId -UserInstallStateSummaryId $userInstallStateSummaryId -BodyParameter $params

```