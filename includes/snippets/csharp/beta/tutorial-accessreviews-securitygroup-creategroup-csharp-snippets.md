---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Group
{
	Description = "Building security",
	DisplayName = "Building security",
	GroupTypes = new List<string>
	{
	},
	MailEnabled = false,
	MailNickname = "buildingsecurity",
	SecurityEnabled = true,
	AdditionalData = new Dictionary<string, object>
	{
		{
			"owners@odata.bind" , new List<string>
			{
				"https://graph.microsoft.com/beta/users/d3bcdff4-4f80-4418-a65e-7bf3778c5dca",
			}
		},
		{
			"members@odata.bind" , new List<string>
			{
				"https://graph.microsoft.com/beta/users/3b8ceebc-49e6-4e0c-9e14-c906374a7ef6",
				"https://graph.microsoft.com/beta/users/bf59c5ba-5304-4c9b-9192-e5a4cb8444e7",
			}
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Groups.PostAsync(requestBody);


```