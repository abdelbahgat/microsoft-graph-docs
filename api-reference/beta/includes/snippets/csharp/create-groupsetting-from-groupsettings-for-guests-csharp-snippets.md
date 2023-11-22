---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new DirectorySetting
{
	TemplateId = "08d542b9-071f-4e16-94b0-74abb372e3d9",
	Values = new List<SettingValue>
	{
		new SettingValue
		{
			Name = "AllowToAddGuests",
			Value = "false",
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Groups["{group-id}"].Settings.PostAsync(requestBody);


```