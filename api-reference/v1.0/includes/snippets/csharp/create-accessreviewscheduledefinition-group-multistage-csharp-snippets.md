---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new AccessReviewScheduleDefinition
{
	DisplayName = "Group Multi-stage Access Review",
	DescriptionForAdmins = "New scheduled access review",
	DescriptionForReviewers = "If you have any questions, contact jerry@contoso.com",
	Scope = new AccessReviewQueryScope
	{
		OdataType = "#microsoft.graph.accessReviewQueryScope",
		Query = "/groups/02f3bafb-448c-487c-88c2-5fd65ce49a41/transitiveMembers",
		QueryType = "MicrosoftGraph",
	},
	StageSettings = new List<AccessReviewStageSettings>
	{
		new AccessReviewStageSettings
		{
			StageId = "1",
			DurationInDays = 2,
			RecommendationsEnabled = false,
			DecisionsThatWillMoveToNextStage = new List<string>
			{
				"NotReviewed",
				"Approve",
			},
			Reviewers = new List<AccessReviewReviewerScope>
			{
				new AccessReviewReviewerScope
				{
					Query = "/users/398164b1-5196-49dd-ada2-364b49f99b27",
					QueryType = "MicrosoftGraph",
				},
			},
		},
		new AccessReviewStageSettings
		{
			StageId = "2",
			DependsOn = new List<string>
			{
				"1",
			},
			DurationInDays = 2,
			RecommendationsEnabled = true,
			Reviewers = new List<AccessReviewReviewerScope>
			{
				new AccessReviewReviewerScope
				{
					Query = "./manager",
					QueryType = "MicrosoftGraph",
					QueryRoot = "decisions",
				},
			},
			FallbackReviewers = new List<AccessReviewReviewerScope>
			{
				new AccessReviewReviewerScope
				{
					Query = "/groups/072ac5f4-3f13-4088-ab30-0a276f3e6322/transitiveMembers",
					QueryType = "MicrosoftGraph",
				},
			},
		},
	},
	Settings = new AccessReviewScheduleSettings
	{
		InstanceDurationInDays = 4,
		Recurrence = new PatternedRecurrence
		{
			Pattern = new RecurrencePattern
			{
				Type = RecurrencePatternType.Weekly,
				Interval = 1,
			},
			Range = new RecurrenceRange
			{
				Type = RecurrenceRangeType.NoEnd,
				StartDate = new Date(DateTime.Parse("2020-09-08T12:02:30.667Z")),
			},
		},
		DecisionHistoriesForReviewersEnabled = true,
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.AccessReviews.Definitions.PostAsync(requestBody);


```