---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var notebook = new Notebook
{
	DisplayName = "My Private notebook"
};

await graphClient.Me.Onenote.Notebooks
	.Request()
	.AddAsync(notebook);

```