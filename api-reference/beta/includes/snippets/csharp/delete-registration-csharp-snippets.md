---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

await graphClient.Me.OnlineMeetings["{onlineMeeting-id}"].Registration.DeleteAsync();


```