---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Me.OnlineMeetings.CreateOrGet;
using Microsoft.Graph.Beta.Models;

var requestBody = new CreateOrGetPostRequestBody
{
	ChatInfo = new ChatInfo
	{
		ThreadId = "19:7ebda77322dd4505ac4dedb5b67df076@thread.tacv2",
	},
	StartDateTime = DateTimeOffset.Parse("2020-02-06T01:49:21.3524945+00:00"),
	EndDateTime = DateTimeOffset.Parse("2020-02-06T02:19:21.3524945+00:00"),
	ExternalId = "7eb8263f-d0e0-4149-bb1c-1f0476083c56",
	Participants = new MeetingParticipants
	{
		Attendees = new List<MeetingParticipantInfo>
		{
			new MeetingParticipantInfo
			{
				Identity = new IdentitySet
				{
					User = new Identity
					{
						Id = "1f35f2e6-9cab-44ad-8d5a-b74c14720000",
					},
				},
				Upn = "test1@contoso.com",
			},
		},
	},
	Subject = "Create a meeting with customId provided",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.OnlineMeetings.CreateOrGet.PostAsync(requestBody);


```