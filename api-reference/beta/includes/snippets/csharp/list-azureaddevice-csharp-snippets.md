---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var updatableAssets = await graphClient.Admin.Windows.Updates.UpdatableAssets
	.Request()
	.Filter("isof('microsoft.graph.windowsUpdates.azureADDevice')")
	.GetAsync();

```