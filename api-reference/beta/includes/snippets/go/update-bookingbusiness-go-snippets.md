---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewBookingBusiness()
email := "admin@fabrikam.com"
requestBody.SetEmail(&email) 
schedulingPolicy := graphmodels.NewBookingSchedulingPolicy()
timeSlotInterval := "PT60M"
schedulingPolicy.SetTimeSlotInterval(&timeSlotInterval) 
minimumLeadTime := "P1D"
schedulingPolicy.SetMinimumLeadTime(&minimumLeadTime) 
maximumAdvance := "P30D"
schedulingPolicy.SetMaximumAdvance(&maximumAdvance) 
sendConfirmationsToOwner := true
schedulingPolicy.SetSendConfirmationsToOwner(&sendConfirmationsToOwner) 
allowStaffSelection := true
schedulingPolicy.SetAllowStaffSelection(&allowStaffSelection) 
requestBody.SetSchedulingPolicy(schedulingPolicy)

graphClient.BookingBusinessesById("bookingBusiness-id").Patch(requestBody)


```