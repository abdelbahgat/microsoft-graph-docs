---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.Drives["{drive-id}"].Items["{driveItem-id}"].Delta.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Token = "2021-09-29T20:00:00Z";
});


```