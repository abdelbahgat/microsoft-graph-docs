---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

await graphClient.Groups["{group-id}"].RejectedSenders.Ref.DeleteAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Id = "https://graph.microsoft.com/v1.0/users/{user-id}";
});


```