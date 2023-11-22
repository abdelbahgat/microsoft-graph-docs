---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new OpenShiftChangeRequest
{
	SenderMessage = "Can I take this shift?",
	OpenShiftId = "577b75d2-a927-48c0-a5d1-dc984894e7b8",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Teams["{team-id}"].Schedule.OpenShiftChangeRequests.PostAsync(requestBody, (requestConfiguration) =>
{
	requestConfiguration.Headers.Add("Authorization", "Bearer {token}");
});


```