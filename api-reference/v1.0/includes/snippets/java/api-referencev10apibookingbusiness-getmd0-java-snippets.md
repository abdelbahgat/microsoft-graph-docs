---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

BookingBusiness bookingBusiness = graphClient.solutions().bookingBusinesses("Fabrikam@contoso.onmicrosoft.com")
	.buildRequest()
	.get();

```