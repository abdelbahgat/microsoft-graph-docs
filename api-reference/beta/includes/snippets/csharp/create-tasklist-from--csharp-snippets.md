---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var baseTaskList = new TaskList
{
	DisplayName = "Shopping list"
};

await graphClient.Me.Tasks.Lists
	.Request()
	.AddAsync(baseTaskList);

```