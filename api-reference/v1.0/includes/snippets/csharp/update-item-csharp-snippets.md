---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var driveItem = new DriveItem
{
	Name = "new-file-name.docx"
};

await graphClient.Me.Drive.Items["{driveItem-id}"]
	.Request()
	.UpdateAsync(driveItem);

```