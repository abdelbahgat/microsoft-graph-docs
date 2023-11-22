---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Me.GetMailTips;
using Microsoft.Graph.Beta.Models;

var requestBody = new GetMailTipsPostRequestBody
{
	EmailAddresses = new List<string>
	{
		"danas@contoso.onmicrosoft.com",
		"fannyd@contoso.onmicrosoft.com",
	},
	MailTipsOptions = MailTipsType.AutomaticReplies | MailTipsType.MailboxFullStatus,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.GetMailTips.PostAsync(requestBody);


```