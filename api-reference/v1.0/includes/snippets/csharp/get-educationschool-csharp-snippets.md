---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var educationSchool = await graphClient.Education.Schools["{educationSchool-id}"]
	.Request()
	.GetAsync();

```