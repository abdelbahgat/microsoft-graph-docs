---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

BookingBusiness bookingBusiness = new BookingBusiness();
bookingBusiness.email = "admin@fabrikam.com";
BookingSchedulingPolicy schedulingPolicy = new BookingSchedulingPolicy();
schedulingPolicy.timeSlotInterval = DatatypeFactory.newInstance().newDuration("PT60M");
schedulingPolicy.minimumLeadTime = DatatypeFactory.newInstance().newDuration("P1D");
schedulingPolicy.maximumAdvance = DatatypeFactory.newInstance().newDuration("P30D");
schedulingPolicy.sendConfirmationsToOwner = true;
schedulingPolicy.allowStaffSelection = true;
bookingBusiness.schedulingPolicy = schedulingPolicy;

graphClient.bookingBusinesses("fabrikam@contoso.onmicrosoft.com")
	.buildRequest()
	.patch(bookingBusiness);

```