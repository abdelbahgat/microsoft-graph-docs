---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Teams.Item.SendActivityNotification.SendActivityNotificationPostRequestBody
{
	Topic = new TeamworkActivityTopic
	{
		Source = TeamworkActivityTopicSource.EntityUrl,
		Value = "https://graph.microsoft.com/v1.0/teams/{teamId}",
	},
	ActivityType = "taskCreated",
	PreviewText = new ItemBody
	{
		Content = "New Task Created",
	},
	Recipient = new TeamworkNotificationRecipient
	{
		OdataType = "microsoft.graph.aadUserNotificationRecipient",
		AdditionalData = new Dictionary<string, object>
		{
			{
				"userId" , "569363e2-4e49-4661-87f2-16f245c5d66a"
			},
		},
	},
	TemplateParameters = new List<KeyValuePair>
	{
		new KeyValuePair
		{
			Name = "taskId",
			Value = "12322",
		},
	},
};
await graphClient.Teams["{team-id}"].SendActivityNotification.PostAsync(requestBody);


```