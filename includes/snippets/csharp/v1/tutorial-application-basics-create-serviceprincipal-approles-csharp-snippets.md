---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Application
{
	AppRoles = new List<AppRole>
	{
		new AppRole
		{
			AllowedMemberTypes = new List<string>
			{
				"User",
				"Application",
			},
			Description = "Survey.Read",
			DisplayName = "Survey.Read",
			Id = Guid.Parse("7a9ddfc4-cc8a-48ea-8275-8ecbffffd5a0"),
			IsEnabled = false,
			Origin = "Application",
			Value = "Survey.Read",
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Applications["{application-id}"].PatchAsync(requestBody);


```