---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.Me.Todo.Lists["{todoTaskList-id}"]
	.Request()
	.DeleteAsync();

```