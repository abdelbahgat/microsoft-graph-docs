---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.Me.Onenote.Notebooks["{notebook-id}"].SectionGroups.GetAsync();


```