---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.DirectoryNamespace.Recommendations.Item.ImpactedResources.Item.Dismiss;

var requestBody = new DismissPostRequestBody
{
	DismissReason = "Application is no longer needed.",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Directory.Recommendations["{recommendation-id}"].ImpactedResources["{impactedResource-id}"].Dismiss.PostAsync(requestBody);


```