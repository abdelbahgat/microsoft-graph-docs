---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Windows10SecureAssessmentConfiguration
{
	OdataType = "#microsoft.graph.windows10SecureAssessmentConfiguration",
	Description = "Description value",
	DisplayName = "Display Name value",
	Version = 7,
	LaunchUri = "Launch Uri value",
	ConfigurationAccount = "Configuration Account value",
	AllowPrinting = true,
	AllowScreenCapture = true,
	AllowTextSuggestion = true,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.DeviceManagement.DeviceConfigurations["{deviceConfiguration-id}"].PatchAsync(requestBody);


```