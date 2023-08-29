---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var message = new Message
{
	Subject = "Party planning",
	ToRecipients = new List<Recipient>()
	{
		new Recipient
		{
			EmailAddress = new EmailAddress
			{
				Name = "Samantha Booth",
				Address = "samanthab@contoso.onmicrosoft.com"
			}
		}
	},
	Mentions = new MessageMentionsCollectionPage()
	{
		new Mention
		{
			Mentioned = new EmailAddress
			{
				Name = "Dana Swope",
				Address = "danas@contoso.onmicrosoft.com"
			}
		}
	}
};

await graphClient.Me.Messages
	.Request()
	.AddAsync(message);

```