---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var skillProficiency = await graphClient.Me.Profile.Skills["{skillProficiency-id}"]
	.Request()
	.GetAsync();

```