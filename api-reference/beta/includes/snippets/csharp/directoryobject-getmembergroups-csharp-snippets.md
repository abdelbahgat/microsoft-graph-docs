---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var securityEnabledOnly = false;

await graphClient.DirectoryObjects["{directoryObject-id}"]
	.GetMemberGroups(securityEnabledOnly)
	.Request()
	.PostAsync();

```