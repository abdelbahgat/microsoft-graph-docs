---
description: "Automatically generated file. DO NOT MODIFY"
---

```csharp

var graphClient = new GraphServiceClient(requestAdapter);

var result = await graphClient.BookingBusinesses["{bookingBusiness-id}"].Customers["{bookingCustomer-id}"].GetAsync();


```