---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.Me.CalendarGroups["{calendarGroup-id}"].Calendars.GetAsync();


```