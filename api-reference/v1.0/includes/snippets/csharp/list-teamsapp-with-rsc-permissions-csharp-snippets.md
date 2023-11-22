---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.AppCatalogs.TeamsApps.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Filter = "id eq 'a5228c26-a9ae-4702-90e0-79a5246d2f7d'";
	requestConfiguration.QueryParameters.Expand = new string []{ "appDefinitions($select=id,authorization)" };
});


```