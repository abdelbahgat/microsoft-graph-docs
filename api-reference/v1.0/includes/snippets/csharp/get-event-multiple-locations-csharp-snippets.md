---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var @event = await graphClient.Me.Events["{event-id}"]
	.Request()
	.Select("subject,body,bodyPreview,organizer,attendees,start,end,location,locations")
	.GetAsync();

```