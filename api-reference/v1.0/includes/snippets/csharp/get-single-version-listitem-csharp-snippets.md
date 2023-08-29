---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var queryOptions = new List<QueryOption>()
{
	new QueryOption("expand", "fields")
};

var listItemVersion = await graphClient.Sites["{site-id}"].Lists["{list-id}"].Items["{listItem-id}"].Versions["{listItemVersion-id}"]
	.Request( queryOptions )
	.GetAsync();

```