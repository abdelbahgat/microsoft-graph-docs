---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var timeOffReasons = await graphClient.Teams["{team-id}"].Schedule.TimeOffReasons
	.Request()
	.GetAsync();

```