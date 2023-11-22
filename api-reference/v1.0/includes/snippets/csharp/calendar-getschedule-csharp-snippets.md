---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Me.Calendar.GetSchedule;
using Microsoft.Graph.Models;

var requestBody = new GetSchedulePostRequestBody
{
	Schedules = new List<string>
	{
		"adelev@contoso.onmicrosoft.com",
		"meganb@contoso.onmicrosoft.com",
	},
	StartTime = new DateTimeTimeZone
	{
		DateTime = "2019-03-15T09:00:00",
		TimeZone = "Pacific Standard Time",
	},
	EndTime = new DateTimeTimeZone
	{
		DateTime = "2019-03-15T18:00:00",
		TimeZone = "Pacific Standard Time",
	},
	AvailabilityViewInterval = 60,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.Calendar.GetSchedule.PostAsync(requestBody, (requestConfiguration) =>
{
	requestConfiguration.Headers.Add("Prefer", "outlook.timezone=\"Pacific Standard Time\"");
});


```