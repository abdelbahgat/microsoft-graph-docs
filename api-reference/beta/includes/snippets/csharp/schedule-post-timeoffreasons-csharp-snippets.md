---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

GraphServiceClient graphClient = new GraphServiceClient( authProvider );

var timeOffReason = new TimeOffReason
{
	DisplayName = "Vacation",
	IconType = TimeOffReasonIconType.Plane,
	IsActive = true
};

await graphClient.Teams["{team-id}"].Schedule.TimeOffReasons
	.Request()
	.AddAsync(timeOffReason);

```