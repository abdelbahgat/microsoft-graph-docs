---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new ChatMessage
{
	Body = new ItemBody
	{
		ContentType = BodyType.Html,
		Content = "Hello World <at id=\"0\">Jane Smith</at>",
	},
	Mentions = new List<ChatMessageMention>
	{
		new ChatMessageMention
		{
			Id = 0,
			MentionText = "Jane Smith",
			Mentioned = new ChatMessageMentionedIdentitySet
			{
				User = new Identity
				{
					DisplayName = "Jane Smith",
					Id = "ef1c916a-3135-4417-ba27-8eb7bd084193",
					AdditionalData = new Dictionary<string, object>
					{
						{
							"userIdentityType" , "aadUser"
						},
					},
				},
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Teams["{team-id}"].Channels["{channel-id}"].Messages.PostAsync(requestBody);


```