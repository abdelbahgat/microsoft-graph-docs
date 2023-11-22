---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new ProjectParticipation
{
	Categories = new List<string>
	{
		"Branding",
	},
	Client = new CompanyDetail
	{
		DisplayName = "Contoso Ltd.",
		Department = "Corporate Marketing",
		WebUrl = "https://www.contoso.com",
	},
	DisplayName = "Contoso Re-branding Project",
	Detail = new PositionDetail
	{
		Company = new CompanyDetail
		{
			DisplayName = "Adventureworks Inc.",
			Department = "Consulting",
			WebUrl = "https://adventureworks.com",
		},
		Description = "Rebranding of Contoso Ltd.",
		JobTitle = "Lead PM Rebranding",
		Role = "project management",
		Summary = "A 6 month project to help Contoso rebrand after they were divested from a parent organization.",
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.Profile.Projects.PostAsync(requestBody);


```