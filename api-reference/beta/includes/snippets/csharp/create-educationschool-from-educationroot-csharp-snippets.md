---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new EducationSchool
{
	DisplayName = "Fabrikam High School",
	Description = "Magnate school for the arts. Los Angeles School District",
	ExternalSource = EducationExternalSource.Sis,
	PrincipalEmail = "AmyR@fabrikam.com",
	PrincipalName = "Amy Roebuck",
	ExternalPrincipalId = "14007",
	HighestGrade = "12",
	LowestGrade = "9",
	SchoolNumber = "10002",
	Address = new PhysicalAddress
	{
		City = "Los Angeles",
		CountryOrRegion = "United States",
		PostalCode = "98055",
		State = "CA",
		Street = "12345 Main St.",
	},
	ExternalId = "10002",
	Phone = "+1 (253) 555-0102",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Education.Schools.PostAsync(requestBody);


```