---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.Chats["{chat-id}"].Tabs.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.Expand = new string []{ "teamsApp" };
	requestConfiguration.QueryParameters.Filter = "teamsApp/id eq 'com.microsoft.teamspace.tab.web'";
});


```