---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var teachers = await graphClient.Education.Classes["{educationClass-id}"].Teachers
	.Request()
	.GetAsync();

```