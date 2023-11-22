---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Application
{
	RequiredResourceAccess = new List<RequiredResourceAccess>
	{
		new RequiredResourceAccess
		{
			ResourceAppId = "00000002-0000-0000-c000-000000000000",
			ResourceAccess = new List<ResourceAccess>
			{
				new ResourceAccess
				{
					Id = Guid.Parse("311a71cc-e848-46a1-bdf8-97ff7156d8e6"),
					Type = "Scope",
				},
				new ResourceAccess
				{
					Id = Guid.Parse("3afa6a7d-9b1a-42eb-948e-1650a849e176"),
					Type = "Role",
				},
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Applications["{application-id}"].PatchAsync(requestBody);


```