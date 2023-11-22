---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new WorkPosition
{
	Detail = new PositionDetail
	{
		Company = new CompanyDetail
		{
			DisplayName = "Adventureworks Ltd.",
			Department = "Consulting",
			OfficeLocation = "AW23/344",
			Address = new PhysicalAddress
			{
				Type = PhysicalAddressType.Business,
				Street = "123 Patriachy Ponds",
				City = "Moscow",
				CountryOrRegion = "Russian Federation",
				PostalCode = "RU-34621",
			},
			WebUrl = "https://www.adventureworks.com",
		},
		JobTitle = "Senior Product Branding Manager II",
		Role = "consulting",
	},
	IsCurrent = true,
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.Profile.Positions.PostAsync(requestBody);


```