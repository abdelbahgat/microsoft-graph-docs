---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var queryOptions = new List<QueryOption>()
{
	new QueryOption("$count", "true")
};

var user = await graphClient.Groups["{group-id}"].TransitiveMembers
	.Request( queryOptions )
	.Header("ConsistencyLevel","eventual")
	.Search("displayName:tier")
	.Select("displayName,id")
	.OrderBy("displayName")
	.GetAsync();

```