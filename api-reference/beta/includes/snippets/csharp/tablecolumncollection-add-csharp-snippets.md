---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var index = new Int32
{
};

var values = JsonDocument.Parse("[{}]");

await graphClient.Me.Drive.Items["{driveItem-id}"].Workbook.Tables["{workbookTable-id}"].Columns
	.Add(index,values,null)
	.Request()
	.PostAsync();

```