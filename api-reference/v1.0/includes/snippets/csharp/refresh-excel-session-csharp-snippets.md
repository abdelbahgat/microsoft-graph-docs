---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.Me.Drive.Items["{driveItem-id}"].Workbook
	.RefreshSession()
	.Request()
	.Header("workbook-session-id","{session-id}")
	.PostAsync();

```