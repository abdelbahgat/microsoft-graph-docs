---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.Me.Messages.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Orderby = new string []{ "from/emailAddress/address" };
});


```