---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var personName = await graphClient.Me.Profile.Names["{personName-id}"]
	.Request()
	.GetAsync();

```