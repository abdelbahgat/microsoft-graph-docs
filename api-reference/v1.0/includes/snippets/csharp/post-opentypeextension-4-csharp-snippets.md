---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Groups.Item.Threads.Item.Posts.Item.Reply;
using Microsoft.Graph.Models;

var requestBody = new ReplyPostRequestBody
{
	Post = new Post
	{
		Body = new ItemBody
		{
			ContentType = BodyType.Html,
			Content = "<html><body><div><div><div><div>When and where? </div></div></div></div></body></html>",
		},
		Extensions = new List<Extension>
		{
			new OpenTypeExtension
			{
				OdataType = "microsoft.graph.openTypeExtension",
				ExtensionName = "Com.Contoso.HR",
				AdditionalData = new Dictionary<string, object>
				{
					{
						"companyName" , "Contoso"
					},
					{
						"expirationDate" , "2015-07-03T13:04:00.000Z"
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
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
await graphClient.Groups["{group-id}"].Threads["{conversationThread-id}"].Posts["{post-id}"].Reply.PostAsync(requestBody);


```