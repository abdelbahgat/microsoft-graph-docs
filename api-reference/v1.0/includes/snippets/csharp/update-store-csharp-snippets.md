---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Models.TermStore.Store
{
	DefaultLanguageTag = "en-US",
};
var result = await graphClient.Sites["{site-id}"].TermStore.PatchAsync(requestBody);


```