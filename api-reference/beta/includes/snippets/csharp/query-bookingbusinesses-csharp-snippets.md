---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.BookingBusinesses.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Query = "Adventure";
});


```