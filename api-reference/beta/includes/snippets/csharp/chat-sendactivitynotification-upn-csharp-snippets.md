---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Beta.Chats.Item.SendActivityNotification.SendActivityNotificationPostRequestBody
{
	Topic = new TeamworkActivityTopic
	{
		Source = TeamworkActivityTopicSource.EntityUrl,
		Value = "https://graph.microsoft.com/beta/chats/{chatId}/messages/{messageId}",
	},
	ActivityType = "approvalRequired",
	PreviewText = new ItemBody
	{
		Content = "Deployment requires your approval",
	},
	Recipient = new TeamworkNotificationRecipient
	{
		OdataType = "microsoft.graph.aadUserNotificationRecipient",
		AdditionalData = new Dictionary<string, object>
		{
			{
				"userId" , "jacob@contoso.com"
			},
		},
	},
	TemplateParameters = new List<KeyValuePair>
	{
		new KeyValuePair
		{
			Name = "approvalTaskId",
			Value = "2020AAGGTAPP",
		},
	},
};
await graphClient.Chats["{chat-id}"].SendActivityNotification.PostAsync(requestBody);


```