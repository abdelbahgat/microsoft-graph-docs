---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Organization
{
	MarketingNotificationEmails = new List<string>
	{
		"marketing@contoso.com",
	},
	PrivacyProfile = new PrivacyProfile
	{
		ContactEmail = "alice@contoso.com",
		StatementUrl = "https://contoso.com/privacyStatement",
	},
	SecurityComplianceNotificationMails = new List<string>
	{
		"security@contoso.com",
	},
	SecurityComplianceNotificationPhones = new List<string>
	{
		"(123) 456-7890",
	},
	TechnicalNotificationMails = new List<string>
	{
		"tech@contoso.com",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Organization["{organization-id}"].PatchAsync(requestBody);


```