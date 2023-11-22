---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new TiIndicator
{
	Action = TiAction.Alert,
	ActivityGroupNames = new List<string>
	{
	},
	Confidence = 0,
	Description = "This is a canary indicator for demo purpose. Take no action on any observables set in this indicator.",
	ExpirationDateTime = DateTimeOffset.Parse("2019-03-01T21:43:37.5031462+00:00"),
	ExternalId = "Test--8586509942679764298MS501",
	FileHashType = FileHashType.Sha256,
	FileHashValue = "aa64428647b57bf51524d1756b2ed746e5a3f31b67cf7fe5b5d8a9daf07ca313",
	KillChain = new List<string>
	{
	},
	MalwareFamilyNames = new List<string>
	{
	},
	Severity = 0,
	Tags = new List<string>
	{
	},
	TargetProduct = "Azure Sentinel",
	ThreatType = "WatchList",
	TlpLevel = TlpLevel.Green,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Security.TiIndicators.PostAsync(requestBody);


```