---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new CloudPcDeviceImage
{
	OdataType = "#microsoft.graph.cloudPcDeviceImage",
	DisplayName = "Display Name value",
	OsBuildNumber = "OS Build Number value",
	OperatingSystem = "Operating System value",
	Version = "Version value",
	SourceImageResourceId = "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c58ffff/resourceGroups/Example/providers/Microsoft.Compute/images/exampleImage",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.DeviceManagement.VirtualEndpoint.DeviceImages.PostAsync(requestBody);


```