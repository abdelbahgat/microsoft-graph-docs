---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var type = "embed";

await graphClient.Me.Drive.Items["{driveItem-id}"]
	.CreateLink(type,null,null,null,null,null)
	.Request()
	.PostAsync();

```