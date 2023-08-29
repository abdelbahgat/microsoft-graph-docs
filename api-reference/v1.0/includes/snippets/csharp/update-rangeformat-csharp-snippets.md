---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var workbookRangeFormat = new WorkbookRangeFormat
{
	ColumnWidth = 135,
	VerticalAlignment = "Top",
	RowHeight = 49,
	WrapText = false
};

await graphClient.Me.Drive.Items["{driveItem-id}"].Workbook.Worksheets["{workbookWorksheet-id}"]
	.Range("$A$1").Format
	.Request()
	.UpdateAsync(workbookRangeFormat);

```