---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.Me.Profile.WebAccounts["{webAccount-id}"]
	.Request()
	.DeleteAsync();

```