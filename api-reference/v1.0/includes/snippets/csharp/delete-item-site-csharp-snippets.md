---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.Sites["{site-id}"].Lists["{list-id}"].Items["{listItem-id}"]
	.Request()
	.DeleteAsync();

```