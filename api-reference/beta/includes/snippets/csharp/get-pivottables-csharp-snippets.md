---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var pivotTables = await graphClient.Drive.Root.Workbook.Worksheets["{workbookWorksheet-id}"].PivotTables
	.Request()
	.GetAsync();

```