---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

// Code snippets are only available for the latest version. Current version is 5.x

// Dependencies
using Microsoft.Graph.Beta.Models;

var requestBody = new BookingCustomer
{
	DisplayName = "Joni Sherman",
	EmailAddress = "jonis@relecloud.com",
	Addresses = new List<PhysicalAddress>
	{
		new PhysicalAddress
		{
			PostOfficeBox = "",
			Street = "4567 Main Street",
			City = "Buffalo",
			State = "NY",
			CountryOrRegion = "USA",
			PostalCode = "98052",
			Type = PhysicalAddressType.Home,
		},
		new PhysicalAddress
		{
			PostOfficeBox = "",
			Street = "4570 Main Street",
			City = "Buffalo",
			State = "NY",
			CountryOrRegion = "USA",
			PostalCode = "98054",
			Type = PhysicalAddressType.Business,
		},
	},
	Phones = new List<Phone>
	{
		new Phone
		{
			Number = "206-555-0100",
			Type = PhoneType.Home,
		},
		new Phone
		{
			Number = "206-555-0200",
			Type = PhoneType.Business,
		},
	},
};

// To initialize your graphClient, see https://learn.microsoft.com/en-us/graph/sdks/create-client?from=snippets&tabs=csharp
var result = await graphClient.BookingBusinesses["{bookingBusiness-id}"].Customers.PostAsync(requestBody);


```