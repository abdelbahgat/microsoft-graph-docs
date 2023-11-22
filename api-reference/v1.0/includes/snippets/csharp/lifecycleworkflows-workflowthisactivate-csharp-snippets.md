---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.IdentityGovernance.LifecycleWorkflows.Workflows.Item.MicrosoftGraphIdentityGovernanceActivate;
using Microsoft.Graph.Models;

var requestBody = new ActivatePostRequestBody
{
	Subjects = new List<User>
	{
		new User
		{
			Id = "8cdf25a8-c9d2-423e-a03d-3f39f03c3e97",
		},
		new User
		{
			Id = "ea09ac2e-77e3-4134-85f2-25ccf3c33387",
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
await graphClient.IdentityGovernance.LifecycleWorkflows.Workflows["{workflow-id}"].MicrosoftGraphIdentityGovernanceActivate.PostAsync(requestBody);


```