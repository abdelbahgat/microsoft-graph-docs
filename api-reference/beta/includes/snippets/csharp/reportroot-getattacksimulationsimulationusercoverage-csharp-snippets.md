---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var getAttackSimulationSimulationUserCoverage = await graphClient.Reports
	.GetAttackSimulationSimulationUserCoverage()
	.Request()
	.GetAsync();

```