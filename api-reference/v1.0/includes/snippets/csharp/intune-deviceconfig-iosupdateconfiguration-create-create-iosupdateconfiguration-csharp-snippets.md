---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new IosUpdateConfiguration
{
	OdataType = "#microsoft.graph.iosUpdateConfiguration",
	Description = "Description value",
	DisplayName = "Display Name value",
	Version = 7,
	ActiveHoursStart = new Time(DateTime.Parse("12:00:05.5020000")),
	ActiveHoursEnd = new Time(DateTime.Parse("11:59:00.8990000")),
	ScheduledInstallDays = new List<DayOfWeekObject?>
	{
		DayOfWeekObject.Monday,
	},
	UtcTimeOffsetInMinutes = 6,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.DeviceManagement.DeviceConfigurations.PostAsync(requestBody);


```