---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var members = await graphClient.Me.Chats["{chat-id}"].Members
	.Request()
	.GetAsync();

```