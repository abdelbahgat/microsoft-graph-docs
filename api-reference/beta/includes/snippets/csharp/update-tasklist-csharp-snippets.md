---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var baseTaskList = new TaskList
{
	DisplayName = "Travel Plan"
};

await graphClient.Me.Tasks.Lists["{baseTaskList-id}"]
	.Request()
	.UpdateAsync(baseTaskList);

```