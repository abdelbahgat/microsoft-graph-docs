---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var persistChanges = true;

await graphClient.Me.Drive.Items["{driveItem-id}"].Workbook
	.CreateSession(persistChanges)
	.Request()
	.PostAsync();

```