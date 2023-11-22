---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new ContentType
{
	Name = "docSet",
	Description = "custom docset",
	Base = new ContentType
	{
		Name = "Document Set",
		Id = "0x0120D520",
	},
	Group = "Document Set Content Types",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Sites["{site-id}"].ContentTypes.PostAsync(requestBody);


```