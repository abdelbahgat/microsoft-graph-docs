---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var b2cIdentityUserFlow = await graphClient.Identity.B2cUserFlows["{b2cIdentityUserFlow-id}"]
	.Request()
	.GetAsync();

```