---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var monthlyPrintUsageByUser = await graphClient.Reports.MonthlyPrintUsageByUser
	.Request()
	.GetAsync();

```