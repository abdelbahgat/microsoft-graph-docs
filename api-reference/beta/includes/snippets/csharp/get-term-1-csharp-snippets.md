---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var term = await graphClient.Sites["{site-id}"].TermStore.Groups["{termStore.group-id}"].Sets["{termStore.set-id}"].Terms["{termStore.term-id}"]
	.Request()
	.GetAsync();

```