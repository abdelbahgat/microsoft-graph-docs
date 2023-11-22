---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Groups["{group-id}"].CalendarView.GetAsync((requestConfiguration) =>
{
	requestConfiguration.QueryParameters.StartDateTime = "2017-01-01T19:00:00-08:00";
	requestConfiguration.QueryParameters.EndDateTime = "2017-10-01T19:00:00.00-08:00";
	requestConfiguration.Headers.Add("Prefer", "outlook.body-content-type=\"text\"");
});


```