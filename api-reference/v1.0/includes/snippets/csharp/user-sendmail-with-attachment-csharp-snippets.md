---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Me.SendMail;
using Microsoft.Graph.Models;

var requestBody = new SendMailPostRequestBody
{
	Message = new Message
	{
		Subject = "Meet for lunch?",
		Body = new ItemBody
		{
			ContentType = BodyType.Text,
			Content = "The new cafeteria is open.",
		},
		ToRecipients = new List<Recipient>
		{
			new Recipient
			{
				EmailAddress = new EmailAddress
				{
					Address = "meganb@contoso.onmicrosoft.com",
				},
			},
		},
		Attachments = new List<Attachment>
		{
			new FileAttachment
			{
				OdataType = "#microsoft.graph.fileAttachment",
				Name = "attachment.txt",
				ContentType = "text/plain",
				ContentBytes = Convert.FromBase64String("SGVsbG8gV29ybGQh"),
			},
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
await graphClient.Me.SendMail.PostAsync(requestBody);


```