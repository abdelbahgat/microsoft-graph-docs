---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models.Security;
using Microsoft.Graph.Beta.Models;

var requestBody = new CategoryTemplate
{
	OdataType = "#microsoft.graph.security.categoryTemplate",
	DisplayName = "String",
	CreatedBy = new IdentitySet
	{
		OdataType = "microsoft.graph.identitySet",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Security.Labels.Categories.PostAsync(requestBody);


```