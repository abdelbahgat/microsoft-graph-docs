---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var simulations = await graphClient.Security.AttackSimulation.Simulations["{simulation-id}"]
	.Request()
	.Select("Report")
	.GetAsync();

var overview = simulations.Report.Overview;

```