---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new PlannerUser
{
	FavoritePlanReferences = new PlannerFavoritePlanReferenceCollection
	{
		AdditionalData = new Dictionary<string, object>
		{
			{
				"jd8S5gOaFk2S8aWCIAJz42QAAxtD" , new PlannerFavoritePlanReference
				{
					OdataType = "#microsoft.graph.plannerFavoritePlanReference",
					OrderHint = " !",
					PlanTitle = "Next Release Discussion",
				}
			},
			{
				"7oTB5aMIAE2rVo-1N-L7RmQAGX2q" , null
			},
		},
	},
	RecentPlanReferences = new PlannerRecentPlanReferenceCollection
	{
		AdditionalData = new Dictionary<string, object>
		{
			{
				"jd8S5gOaFk2S8aWCIAJz42QAAxtD" , new PlannerRecentPlanReference
				{
					OdataType = "#microsoft.graph.plannerRecentPlanReference",
					LastAccessedDateTime = DateTimeOffset.Parse("2018-01-02T22:49:46.155Z"),
					PlanTitle = "Next Release Discussion",
				}
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.Planner.PatchAsync(requestBody, (requestConfiguration) =>
{
	requestConfiguration.Headers.Add("Prefer", "return=representation");
	requestConfiguration.Headers.Add("If-Match", "W/\"JzEtVXNlckRldGFpbHMgQEBAQEBAQEBAQEBAQEBIWCc=\"");
});


```