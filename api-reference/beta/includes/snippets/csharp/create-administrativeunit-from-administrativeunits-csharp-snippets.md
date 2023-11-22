---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new AdministrativeUnit
{
	DisplayName = "Seattle District Technical Schools",
	Description = "Seattle district technical schools administration",
	AdditionalData = new Dictionary<string, object>
	{
		{
			"membershipType" , "Dynamic"
		},
		{
			"membershipRule" , "(user.country -eq \"United States\")"
		},
		{
			"membershipRuleProcessingState" , "On"
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.AdministrativeUnits.PostAsync(requestBody);


```