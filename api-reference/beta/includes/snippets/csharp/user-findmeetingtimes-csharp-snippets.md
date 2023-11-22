---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Me.FindMeetingTimes;
using Microsoft.Graph.Beta.Models;

var requestBody = new FindMeetingTimesPostRequestBody
{
	Attendees = new List<AttendeeBase>
	{
		new AttendeeBase
		{
			Type = AttendeeType.Required,
			EmailAddress = new EmailAddress
			{
				Name = "Alex Wilbur",
				Address = "alexw@contoso.onmicrosoft.com",
			},
		},
	},
	LocationConstraint = new LocationConstraint
	{
		IsRequired = false,
		SuggestLocation = false,
		Locations = new List<LocationConstraintItem>
		{
			new LocationConstraintItem
			{
				ResolveAvailability = false,
				DisplayName = "Conf room Hood",
			},
		},
	},
	TimeConstraint = new TimeConstraint
	{
		ActivityDomain = ActivityDomain.Work,
		TimeSlots = new List<TimeSlot>
		{
			new TimeSlot
			{
				Start = new DateTimeTimeZone
				{
					DateTime = "2019-04-16T09:00:00",
					TimeZone = "Pacific Standard Time",
				},
				End = new DateTimeTimeZone
				{
					DateTime = "2019-04-18T17:00:00",
					TimeZone = "Pacific Standard Time",
				},
			},
		},
	},
	IsOrganizerOptional = false,
	MeetingDuration = TimeSpan.Parse("PT1H"),
	ReturnSuggestionReasons = true,
	MinimumAttendeePercentage = 100d,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.FindMeetingTimes.PostAsync(requestBody, (requestConfiguration) =>
{
	requestConfiguration.Headers.Add("Prefer", "outlook.timezone=\"Pacific Standard Time\"");
});


```