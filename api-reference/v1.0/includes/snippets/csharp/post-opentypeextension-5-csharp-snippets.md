---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Conversation
{
	Topic = "Does anyone have a second?",
	Threads = new List<ConversationThread>
	{
		new ConversationThread
		{
			Posts = new List<Post>
			{
				new Post
				{
					Body = new ItemBody
					{
						ContentType = BodyType.Html,
						Content = "This is urgent!",
					},
					Extensions = new List<Extension>
					{
						new OpenTypeExtension
						{
							OdataType = "microsoft.graph.openTypeExtension",
							ExtensionName = "Com.Contoso.Benefits",
							AdditionalData = new Dictionary<string, object>
							{
								{
									"companyName" , "Contoso"
								},
								{
									"expirationDate" , "2016-08-03T11:00:00.000Z"
								},
								{
									"topPicks" , new List<string>
									{
										"Employees only",
										"Add spouse or guest",
										"Add family",
									}
								},
							},
						},
					},
				},
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Groups["{group-id}"].Conversations.PostAsync(requestBody);


```