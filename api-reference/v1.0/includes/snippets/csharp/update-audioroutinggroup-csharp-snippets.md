---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new AudioRoutingGroup
{
	Id = "oneToOne",
	RoutingMode = RoutingMode.OneToOne,
	Sources = new List<string>
	{
		"632899f8-2ea1-4604-8413-27bd2892079f",
	},
	Receivers = new List<string>
	{
		"550fae72-d251-43ec-868c-373732c2704f",
		"72f988bf-86f1-41af-91ab-2d7cd011db47",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Communications.Calls["{call-id}"].AudioRoutingGroups["{audioRoutingGroup-id}"].PatchAsync(requestBody);


```