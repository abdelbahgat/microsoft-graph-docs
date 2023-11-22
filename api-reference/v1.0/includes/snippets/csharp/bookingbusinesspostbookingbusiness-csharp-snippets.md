---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Models;

var requestBody = new BookingBusiness
{
	DisplayName = "Fourth Coffee",
	Address = new PhysicalAddress
	{
		Street = "4567 Main Street",
		City = "Buffalo",
		State = "NY",
		CountryOrRegion = "USA",
		PostalCode = "98052",
		AdditionalData = new Dictionary<string, object>
		{
			{
				"postOfficeBox" , "P.O. Box 123"
			},
		},
	},
	Phone = "206-555-0100",
	Email = "manager@fourthcoffee.com",
	WebSiteUrl = "https://www.fourthcoffee.com",
	DefaultCurrencyIso = "USD",
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.Solutions.BookingBusinesses.PostAsync(requestBody);


```