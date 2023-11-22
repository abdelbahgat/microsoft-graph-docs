---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new MobileThreatDefenseConnector
{
	OdataType = "#microsoft.graph.mobileThreatDefenseConnector",
	LastHeartbeatDateTime = DateTimeOffset.Parse("2016-12-31T23:59:37.9174975-08:00"),
	PartnerState = MobileThreatPartnerTenantState.Available,
	AndroidMobileApplicationManagementEnabled = true,
	IosMobileApplicationManagementEnabled = true,
	AndroidEnabled = true,
	IosEnabled = true,
	WindowsEnabled = true,
	AndroidDeviceBlockedOnMissingPartnerData = true,
	IosDeviceBlockedOnMissingPartnerData = true,
	WindowsDeviceBlockedOnMissingPartnerData = true,
	PartnerUnsupportedOsVersionBlocked = true,
	PartnerUnresponsivenessThresholdInDays = 6,
	AllowPartnerToCollectIOSApplicationMetadata = true,
	AllowPartnerToCollectIOSPersonalApplicationMetadata = true,
	MicrosoftDefenderForEndpointAttachEnabled = true,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.DeviceManagement.MobileThreatDefenseConnectors.PostAsync(requestBody);


```