---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.RiskyUsers.Dismiss;

var requestBody = new DismissPostRequestBody
{
	UserIds = new List<string>
	{
		"04487ee0-f4f6-4e7f-8999-facc5a30e232",
		"13387ee0-f4f6-4e7f-8999-facc5120e345",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
await graphClient.RiskyUsers.Dismiss.PostAsync(requestBody);


```