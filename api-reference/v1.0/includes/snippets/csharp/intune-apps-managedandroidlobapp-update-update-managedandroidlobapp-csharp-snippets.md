---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new ManagedAndroidLobApp
{
	OdataType = "#microsoft.graph.managedAndroidLobApp",
	DisplayName = "Display Name value",
	Description = "Description value",
	Publisher = "Publisher value",
	LargeIcon = new MimeContent
	{
		OdataType = "microsoft.graph.mimeContent",
		Type = "Type value",
		Value = Convert.FromBase64String("dmFsdWU="),
	},
	IsFeatured = true,
	PrivacyInformationUrl = "https://example.com/privacyInformationUrl/",
	InformationUrl = "https://example.com/informationUrl/",
	Owner = "Owner value",
	Developer = "Developer value",
	Notes = "Notes value",
	PublishingState = MobileAppPublishingState.Processing,
	AppAvailability = ManagedAppAvailability.LineOfBusiness,
	Version = "Version value",
	CommittedContentVersion = "Committed Content Version value",
	FileName = "File Name value",
	Size = 4L,
	PackageId = "Package Id value",
	MinimumSupportedOperatingSystem = new AndroidMinimumOperatingSystem
	{
		OdataType = "microsoft.graph.androidMinimumOperatingSystem",
		V40 = true,
		V403 = true,
		V41 = true,
		V42 = true,
		V43 = true,
		V44 = true,
		V50 = true,
		V51 = true,
		V60 = true,
		V70 = true,
		V71 = true,
		V80 = true,
		V81 = true,
		V90 = true,
		V100 = true,
		V110 = true,
	},
	VersionName = "Version Name value",
	VersionCode = "Version Code value",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.DeviceAppManagement.MobileApps["{mobileApp-id}"].PatchAsync(requestBody);


```