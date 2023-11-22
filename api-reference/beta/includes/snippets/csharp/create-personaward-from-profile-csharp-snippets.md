---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new PersonAward
{
	Description = "Lifetime Achievement award from the International Association of Branding Managers",
	DisplayName = "Lifetime Achievement Award For Excellence in Branding",
	IssuedDate = new Date(DateTime.Parse("Date")),
	IssuingAuthority = "International Association of Branding Management",
	ThumbnailUrl = "https://iabm.io/sdhdfhsdhshsd.jpg",
	WebUrl = "https://www.iabm.io",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Me.Profile.Awards.PostAsync(requestBody);


```