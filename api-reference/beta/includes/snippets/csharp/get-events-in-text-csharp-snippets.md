---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var events = await graphClient.Me.Events
	.Request()
	.Header("Prefer","outlook.body-content-type=\"text\"")
	.Select("subject,body,bodyPreview")
	.GetAsync();

```