---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var delta = await graphClient.Me.Tasks.Lists["{baseTaskList-id}"].Tasks
	.Delta()
	.Request()
	.GetAsync();

```