---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var requestBody = new Microsoft.Graph.Admin.ServiceAnnouncement.Messages.MarkRead.MarkReadPostRequestBody
{
	MessageIds = new List<string>
	{
		"MC172851",
		"MC167983",
	},
};
var result = await graphClient.Admin.ServiceAnnouncement.Messages.MarkRead.PostAsync(requestBody);


```