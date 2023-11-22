---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new MailboxSettings
{
	AutomaticRepliesSetting = new AutomaticRepliesSetting
	{
		Status = AutomaticRepliesStatus.Scheduled,
		ScheduledStartDateTime = new DateTimeTimeZone
		{
			DateTime = "2016-03-20T18:00:00.0000000",
			TimeZone = "UTC",
		},
		ScheduledEndDateTime = new DateTimeTimeZone
		{
			DateTime = "2016-03-28T18:00:00.0000000",
			TimeZone = "UTC",
		},
	},
	AdditionalData = new Dictionary<string, object>
	{
		{
			"@odata.context" , "https://graph.microsoft.com/beta/$metadata#Me/mailboxSettings"
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.MailboxSettings.PatchAsync(requestBody);


```