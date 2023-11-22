---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new Shift
{
	Id = "SHFT_577b75d2-a927-48c0-a5d1-dc984894e7b8",
	UserId = "c5d0c76b-80c4-481c-be50-923cd8d680a1",
	SchedulingGroupId = "TAG_228940ed-ff84-4e25-b129-1b395cf78be0",
	SharedShift = new ShiftItem
	{
		DisplayName = "Day shift",
		Notes = "Please do inventory as part of your shift.",
		StartDateTime = DateTimeOffset.Parse("2019-03-11T15:00:00Z"),
		EndDateTime = DateTimeOffset.Parse("2019-03-12T00:00:00Z"),
		Theme = ScheduleEntityTheme.Blue,
		Activities = new List<ShiftActivity>
		{
			new ShiftActivity
			{
				IsPaid = true,
				StartDateTime = DateTimeOffset.Parse("2019-03-11T15:00:00Z"),
				EndDateTime = DateTimeOffset.Parse("2019-03-11T15:15:00Z"),
				Code = "",
				DisplayName = "Lunch",
			},
		},
	},
	DraftShift = new ShiftItem
	{
		DisplayName = "Day shift",
		Notes = "Please do inventory as part of your shift.",
		StartDateTime = DateTimeOffset.Parse("2019-03-11T15:00:00Z"),
		EndDateTime = DateTimeOffset.Parse("2019-03-12T00:00:00Z"),
		Theme = ScheduleEntityTheme.Blue,
		Activities = new List<ShiftActivity>
		{
			new ShiftActivity
			{
				IsPaid = true,
				StartDateTime = DateTimeOffset.Parse("2019-03-11T15:00:00Z"),
				EndDateTime = DateTimeOffset.Parse("2019-03-11T15:30:00Z"),
				Code = "",
				DisplayName = "Lunch",
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Teams["{team-id}"].Schedule.Shifts.PostAsync(requestBody);


```