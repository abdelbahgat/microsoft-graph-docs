---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var sectionGroup = new SectionGroup
{
	DisplayName = "Section group name"
};

await graphClient.Me.Onenote.Notebooks["{notebook-id}"].SectionGroups
	.Request()
	.AddAsync(sectionGroup);

```