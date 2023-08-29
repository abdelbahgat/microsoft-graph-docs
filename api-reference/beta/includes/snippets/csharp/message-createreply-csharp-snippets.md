---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var message = new Message
{
	ToRecipients = new List<Recipient>()
	{
		new Recipient
		{
			EmailAddress = new EmailAddress
			{
				Address = "samanthab@contoso.onmicrosoft.com",
				Name = "Samantha Booth"
			}
		},
		new Recipient
		{
			EmailAddress = new EmailAddress
			{
				Address = "randiw@contoso.onmicrosoft.com",
				Name = "Randi Welch"
			}
		}
	}
};

var comment = "Samantha, Randi, would you name the group if the project is approved, please?";

await graphClient.Me.Messages["{message-id}"]
	.CreateReply(message,comment)
	.Request()
	.PostAsync();

```