---
description: "Automatically generated file. DO NOT MODIFY"
---

```powershell

Import-Module Microsoft.Graph.DeviceManagement.Actions

$params = @{
	ReviewStatus = @{
		InReview = $true
		UserAccessLevel = "restricted"
		AzureStorageAccountId = "/subscriptions/f68bd846-16ad-4b51-a7c6-c84944a3367c/resourceGroups/Review/providers/Microsoft.Storage/storageAccounts/snapshotsUnderReview"
	}
}

Set-MgDeviceManagementManagedDeviceCloudPcReviewStatus -ManagedDeviceId $managedDeviceId -BodyParameter $params

```