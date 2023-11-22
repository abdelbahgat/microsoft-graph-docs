---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.DeviceManagement.ManagedDevices.BulkSetCloudPcReviewStatus;
using Microsoft.Graph.Beta.Models;

var requestBody = new BulkSetCloudPcReviewStatusPostRequestBody
{
	ManagedDeviceIds = new List<string>
	{
		"30d0e128-de93-41dc-89ec-33d84bb662a0",
		"7c82a3e3-9459-44e4-94d9-b92f93bf78dd",
	},
	ReviewStatus = new CloudPcReviewStatus
	{
		InReview = true,
		UserAccessLevel = CloudPcUserAccessLevel.Restricted,
		AzureStorageAccountId = "/subscriptions/f68bd846-16ad-4b51-a7c6-c84944a3367c/resourceGroups/Review/providers/Microsoft.Storage/storageAccounts/snapshotsUnderReview",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.DeviceManagement.ManagedDevices.BulkSetCloudPcReviewStatus.PostAsync(requestBody);


```