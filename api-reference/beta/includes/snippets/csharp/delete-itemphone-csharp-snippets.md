---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

await graphClient.Users["{user-id}"].Profile.Phones["{itemPhone-id}"].DeleteAsync();


```