---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new MacOSCustomConfiguration
{
	OdataType = "#microsoft.graph.macOSCustomConfiguration",
	Description = "Description value",
	DisplayName = "Display Name value",
	Version = 7,
	PayloadName = "Payload Name value",
	PayloadFileName = "Payload File Name value",
	Payload = Convert.FromBase64String("cGF5bG9hZA=="),
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.DeviceManagement.DeviceConfigurations.PostAsync(requestBody);


```