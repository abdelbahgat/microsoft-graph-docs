---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Group
{
	Description = "Group with designated owner and members",
	DisplayName = "Operations group",
	GroupTypes = new List<string>
	{
	},
	MailEnabled = false,
	MailNickname = "operations2019",
	SecurityEnabled = true,
	AdditionalData = new Dictionary<string, object>
	{
		{
			"owners@odata.bind" , new List<string>
			{
				"https://graph.microsoft.com/v1.0/users/26be1845-4119-4801-a799-aea79d09f1a2",
			}
		},
		{
			"members@odata.bind" , new List<string>
			{
				"https://graph.microsoft.com/v1.0/users/ff7cb387-6688-423c-8188-3da9532a73cc",
				"https://graph.microsoft.com/v1.0/users/69456242-0067-49d3-ba96-9de6f2728e14",
			}
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Groups.PostAsync(requestBody);


```