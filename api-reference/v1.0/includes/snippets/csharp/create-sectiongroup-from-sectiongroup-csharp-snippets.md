---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var sectionGroup = new SectionGroup
{
	DisplayName = "Section group name"
};

await graphClient.Me.Onenote.SectionGroups["{sectionGroup-id}"].SectionGroups
	.Request()
	.AddAsync(sectionGroup);

```