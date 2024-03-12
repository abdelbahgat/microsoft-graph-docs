---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Groups.Item.Threads.Item.Posts.Item.Reply.ReplyPostRequestBody
{
	Post = new Post
	{
		Body = new ItemBody
		{
			ContentType = BodyType.Text,
			Content = "content-value",
		},
		ReceivedDateTime = DateTimeOffset.Parse("datetime-value"),
		HasAttachments = true,
		From = new Recipient
		{
			EmailAddress = new EmailAddress
			{
				Name = "name-value",
				Address = "address-value",
			},
		},
		Sender = new Recipient
		{
			EmailAddress = new EmailAddress
			{
				Name = "name-value",
				Address = "address-value",
			},
		},
		ConversationThreadId = "conversationThreadId-value",
		NewParticipants = new List<Recipient>
		{
			new Recipient
			{
				EmailAddress = new EmailAddress
				{
					Name = "name-value",
					Address = "address-value",
				},
			},
		},
		ConversationId = "conversationId-value",
		CreatedDateTime = DateTimeOffset.Parse("datetime-value"),
		LastModifiedDateTime = DateTimeOffset.Parse("datetime-value"),
		ChangeKey = "changeKey-value",
		Categories = new List<string>
		{
			"categories-value",
		},
		Id = "id-value",
		InReplyTo = new Post
		{
		},
		Attachments = new List<Attachment>
		{
			new Attachment
			{
				OdataType = "#microsoft.graph.fileAttachment",
				LastModifiedDateTime = DateTimeOffset.Parse("datetime-value"),
				Name = "name-value",
				ContentType = "contentType-value",
				Size = 99,
				IsInline = true,
				Id = "id-value",
			},
		},
	},
};
await graphClient.Groups["{group-id}"].Threads["{conversationThread-id}"].Posts["{post-id}"].Reply.PostAsync(requestBody);


```