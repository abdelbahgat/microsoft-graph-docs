---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var directoryObject = await graphClient.Directory.DeletedItems["{directoryObject-id}"]
	.Request()
	.GetAsync();

```