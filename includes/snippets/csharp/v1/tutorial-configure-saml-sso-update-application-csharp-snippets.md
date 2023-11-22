---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new Application
{
	Web = new WebApplication
	{
		RedirectUris = new List<string>
		{
			"https://signin.aws.amazon.com/saml",
		},
	},
	IdentifierUris = new List<string>
	{
		"https://signin.aws.amazon.com/saml",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Applications["{application-id}"].PatchAsync(requestBody);


```