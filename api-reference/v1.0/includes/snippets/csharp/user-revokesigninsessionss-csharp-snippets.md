---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

await graphClient.Me
	.RevokeSignInSessions()
	.Request()
	.PostAsync();

```