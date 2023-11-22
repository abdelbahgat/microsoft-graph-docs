---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new AccessReviewScheduleDefinition
{
	DisplayName = "One-time self-review for members of Building security",
	DescriptionForAdmins = "One-time self-review for members of Building security",
	DescriptionForReviewers = "One-time self-review for members of Building security",
	Scope = new AccessReviewScope
	{
		AdditionalData = new Dictionary<string, object>
		{
			{
				"query" , "/groups/eb75ccd2-59ef-48b7-8f76-cc3f33f899f4/transitiveMembers"
			},
			{
				"queryType" , "MicrosoftGraph"
			},
		},
	},
	InstanceEnumerationScope = new AccessReviewScope
	{
		AdditionalData = new Dictionary<string, object>
		{
			{
				"query" , "/groups/eb75ccd2-59ef-48b7-8f76-cc3f33f899f4"
			},
			{
				"queryType" , "MicrosoftGraph"
			},
		},
	},
	Settings = new AccessReviewScheduleSettings
	{
		MailNotificationsEnabled = true,
		ReminderNotificationsEnabled = true,
		JustificationRequiredOnApproval = true,
		DefaultDecisionEnabled = true,
		DefaultDecision = "Deny",
		InstanceDurationInDays = 5,
		AutoApplyDecisionsEnabled = true,
		RecommendationsEnabled = true,
		Recurrence = new PatternedRecurrence
		{
			Pattern = null,
			Range = new RecurrenceRange
			{
				Type = RecurrenceRangeType.Numbered,
				NumberOfOccurrences = 0,
				RecurrenceTimeZone = null,
				StartDate = new Date(DateTime.Parse("2022-02-11")),
				EndDate = new Date(DateTime.Parse("2022-02-16")),
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.IdentityGovernance.AccessReviews.Definitions.PostAsync(requestBody);


```