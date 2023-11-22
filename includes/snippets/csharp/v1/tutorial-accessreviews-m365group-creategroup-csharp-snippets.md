---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Group
{
	Description = "Feelgood Marketing Campaign with external partners and vendors.",
	DisplayName = "Feelgood Marketing Campaign",
	GroupTypes = new List<string>
	{
		"Unified",
	},
	MailEnabled = true,
	MailNickname = "FeelGoodCampaign",
	SecurityEnabled = true,
	AdditionalData = new Dictionary<string, object>
	{
		{
			"owners@odata.bind" , new List<string>
			{
				"https://graph.microsoft.com/v1.0/users/cdb555e3-b33e-4fd5-a427-17fadacbdfa7",
			}
		},
		{
			"members@odata.bind" , new List<string>
			{
				"https://graph.microsoft.com/v1.0/users/baf1b0a0-1f9a-4a56-9884-6a30824f8d20",
			}
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Groups.PostAsync(requestBody);


```