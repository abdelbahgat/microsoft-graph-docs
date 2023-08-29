---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var workbookChartTitle = new WorkbookChartTitle
{
	Overlay = true,
	Text = "text-value",
	Visible = true
};

await graphClient.Me.Drive.Items["{driveItem-id}"].Workbook.Worksheets["{workbookWorksheet-id}"].Charts["{workbookChart-id}"].Title
	.Request()
	.UpdateAsync(workbookChartTitle);

```