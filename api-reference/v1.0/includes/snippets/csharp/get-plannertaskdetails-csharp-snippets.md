---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var plannerTaskDetails = await graphClient.Planner.Tasks["{plannerTask-id}"].Details
	.Request()
	.GetAsync();

```