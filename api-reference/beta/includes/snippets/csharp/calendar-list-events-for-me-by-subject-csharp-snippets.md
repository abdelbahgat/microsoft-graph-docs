---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.Me.Calendar.Events.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Filter = "startsWith(subject,'All')";
});


```