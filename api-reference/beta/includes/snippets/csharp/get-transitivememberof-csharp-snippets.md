---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var transitiveMemberOf = await graphClient.Users["{user-id}"].TransitiveMemberOf
	.Request()
	.GetAsync();

```