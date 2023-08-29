---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var post = new Post
{
	Body = new ItemBody
	{
		ContentType = BodyType.Text,
		Content = "content-value"
	},
	ReceivedDateTime = DateTimeOffset.Parse("2016-10-19T10:37:00Z"),
	HasAttachments = true,
	From = new Recipient
	{
		EmailAddress = new EmailAddress
		{
			Name = "name-value",
			Address = "address-value"
		}
	},
	Sender = new Recipient
	{
		EmailAddress = new EmailAddress
		{
			Name = "name-value",
			Address = "address-value"
		}
	},
	ConversationThreadId = "conversationThreadId-value",
	NewParticipants = new List<Recipient>()
	{
		new Recipient
		{
			EmailAddress = new EmailAddress
			{
				Name = "name-value",
				Address = "address-value"
			}
		}
	},
	ConversationId = "conversationId-value",
	CreatedDateTime = DateTimeOffset.Parse("2016-10-19T10:37:00Z"),
	LastModifiedDateTime = DateTimeOffset.Parse("2016-10-19T10:37:00Z"),
	ChangeKey = "changeKey-value",
	Categories = new List<String>()
	{
		"categories-value"
	},
	Id = "id-value",
	InReplyTo = new Post
	{
	},
	Attachments = new PostAttachmentsCollectionPage()
	{
		new FileAttachment
		{
			LastModifiedDateTime = DateTimeOffset.Parse("2016-10-19T10:37:00Z"),
			Name = "name-value",
			ContentType = "contentType-value",
			Size = 99,
			IsInline = true,
			Id = "id-value"
		}
	}
};

await graphClient.Groups["{group-id}"].Threads["{conversationThread-id}"].Posts["{post-id}"]
	.Reply(post)
	.Request()
	.PostAsync();

```