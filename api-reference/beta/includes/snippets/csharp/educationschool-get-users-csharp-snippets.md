---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var users = await graphClient.Education.Schools["{educationSchool-id}"].Users
	.Request()
	.GetAsync();

```