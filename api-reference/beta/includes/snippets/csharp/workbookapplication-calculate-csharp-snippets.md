---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var calculationType = "calculationType-value";

await graphClient.Me.Drive.Items["{driveItem-id}"].Workbook.Application
	.Calculate(calculationType)
	.Request()
	.PostAsync();

```