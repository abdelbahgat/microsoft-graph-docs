---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

Int32? index = null;

var values = JsonDocument.Parse("[[1,2,3],[4,5,6]]");

await graphClient.Me.Drive.Items["{driveItem-id}"].Workbook.Tables["{workbookTable-id}"].Rows
	.Add(index,values)
	.Request()
	.PostAsync();

```