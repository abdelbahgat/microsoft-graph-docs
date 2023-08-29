---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewBookingStaffMember()
"@odata.type" := "#microsoft.graph.bookingStaffMember"
requestBody.Set"@odata.type"(&"@odata.type") 
colorIndex := int32(1)
requestBody.SetColorIndex(&colorIndex) 
displayName := "Dana Swope"
requestBody.SetDisplayName(&displayName) 
emailAddress := "danas@contoso.com"
requestBody.SetEmailAddress(&emailAddress) 
role := graphmodels.EXTERNALGUEST_BOOKINGSTAFFROLE 
requestBody.SetRole(&role) 
timeZone := "America/Chicago"
requestBody.SetTimeZone(&timeZone) 
useBusinessHours := true
requestBody.SetUseBusinessHours(&useBusinessHours) 


bookingWorkHours := graphmodels.NewBookingWorkHours()
"@odata.type" := "#microsoft.graph.bookingWorkHours"
bookingWorkHours.Set"@odata.type"(&"@odata.type") 
day := graphmodels.MONDAY_DAYOFWEEK 
bookingWorkHours.SetDay(&day) 


bookingWorkTimeSlot := graphmodels.NewBookingWorkTimeSlot()
"@odata.type" := "#microsoft.graph.bookingWorkTimeSlot"
bookingWorkTimeSlot.Set"@odata.type"(&"@odata.type") 
end := "17:00:00.0000000"
bookingWorkTimeSlot.SetEnd(&end) 
start := "08:00:00.0000000"
bookingWorkTimeSlot.SetStart(&start) 

timeSlots := []graphmodels.BookingWorkTimeSlotable {
	bookingWorkTimeSlot,

}
bookingWorkHours.SetTimeSlots(timeSlots)
additionalData := map[string]interface{}{
	"day@odata.type" : "#microsoft.graph.dayOfWeek", 
	"timeSlots@odata.type" : "#Collection(microsoft.graph.bookingWorkTimeSlot)", 
}
bookingWorkHours.SetAdditionalData(additionalData)
bookingWorkHours1 := graphmodels.NewBookingWorkHours()
"@odata.type" := "#microsoft.graph.bookingWorkHours"
bookingWorkHours1.Set"@odata.type"(&"@odata.type") 
day := graphmodels.TUESDAY_DAYOFWEEK 
bookingWorkHours1.SetDay(&day) 


bookingWorkTimeSlot := graphmodels.NewBookingWorkTimeSlot()
"@odata.type" := "#microsoft.graph.bookingWorkTimeSlot"
bookingWorkTimeSlot.Set"@odata.type"(&"@odata.type") 
end := "17:00:00.0000000"
bookingWorkTimeSlot.SetEnd(&end) 
start := "08:00:00.0000000"
bookingWorkTimeSlot.SetStart(&start) 

timeSlots := []graphmodels.BookingWorkTimeSlotable {
	bookingWorkTimeSlot,

}
bookingWorkHours1.SetTimeSlots(timeSlots)
additionalData := map[string]interface{}{
	"day@odata.type" : "#microsoft.graph.dayOfWeek", 
	"timeSlots@odata.type" : "#Collection(microsoft.graph.bookingWorkTimeSlot)", 
}
bookingWorkHours1.SetAdditionalData(additionalData)
bookingWorkHours2 := graphmodels.NewBookingWorkHours()
"@odata.type" := "#microsoft.graph.bookingWorkHours"
bookingWorkHours2.Set"@odata.type"(&"@odata.type") 
day := graphmodels.WEDNESDAY_DAYOFWEEK 
bookingWorkHours2.SetDay(&day) 


bookingWorkTimeSlot := graphmodels.NewBookingWorkTimeSlot()
"@odata.type" := "#microsoft.graph.bookingWorkTimeSlot"
bookingWorkTimeSlot.Set"@odata.type"(&"@odata.type") 
end := "17:00:00.0000000"
bookingWorkTimeSlot.SetEnd(&end) 
start := "08:00:00.0000000"
bookingWorkTimeSlot.SetStart(&start) 

timeSlots := []graphmodels.BookingWorkTimeSlotable {
	bookingWorkTimeSlot,

}
bookingWorkHours2.SetTimeSlots(timeSlots)
additionalData := map[string]interface{}{
	"day@odata.type" : "#microsoft.graph.dayOfWeek", 
	"timeSlots@odata.type" : "#Collection(microsoft.graph.bookingWorkTimeSlot)", 
}
bookingWorkHours2.SetAdditionalData(additionalData)
bookingWorkHours3 := graphmodels.NewBookingWorkHours()
"@odata.type" := "#microsoft.graph.bookingWorkHours"
bookingWorkHours3.Set"@odata.type"(&"@odata.type") 
day := graphmodels.THURSDAY_DAYOFWEEK 
bookingWorkHours3.SetDay(&day) 


bookingWorkTimeSlot := graphmodels.NewBookingWorkTimeSlot()
"@odata.type" := "#microsoft.graph.bookingWorkTimeSlot"
bookingWorkTimeSlot.Set"@odata.type"(&"@odata.type") 
end := "17:00:00.0000000"
bookingWorkTimeSlot.SetEnd(&end) 
start := "08:00:00.0000000"
bookingWorkTimeSlot.SetStart(&start) 

timeSlots := []graphmodels.BookingWorkTimeSlotable {
	bookingWorkTimeSlot,

}
bookingWorkHours3.SetTimeSlots(timeSlots)
additionalData := map[string]interface{}{
	"day@odata.type" : "#microsoft.graph.dayOfWeek", 
	"timeSlots@odata.type" : "#Collection(microsoft.graph.bookingWorkTimeSlot)", 
}
bookingWorkHours3.SetAdditionalData(additionalData)
bookingWorkHours4 := graphmodels.NewBookingWorkHours()
"@odata.type" := "#microsoft.graph.bookingWorkHours"
bookingWorkHours4.Set"@odata.type"(&"@odata.type") 
day := graphmodels.FRIDAY_DAYOFWEEK 
bookingWorkHours4.SetDay(&day) 


bookingWorkTimeSlot := graphmodels.NewBookingWorkTimeSlot()
"@odata.type" := "#microsoft.graph.bookingWorkTimeSlot"
bookingWorkTimeSlot.Set"@odata.type"(&"@odata.type") 
end := "17:00:00.0000000"
bookingWorkTimeSlot.SetEnd(&end) 
start := "08:00:00.0000000"
bookingWorkTimeSlot.SetStart(&start) 

timeSlots := []graphmodels.BookingWorkTimeSlotable {
	bookingWorkTimeSlot,

}
bookingWorkHours4.SetTimeSlots(timeSlots)
additionalData := map[string]interface{}{
	"day@odata.type" : "#microsoft.graph.dayOfWeek", 
	"timeSlots@odata.type" : "#Collection(microsoft.graph.bookingWorkTimeSlot)", 
}
bookingWorkHours4.SetAdditionalData(additionalData)

workingHours := []graphmodels.BookingWorkHoursable {
	bookingWorkHours,
	bookingWorkHours1,
	bookingWorkHours2,
	bookingWorkHours3,
	bookingWorkHours4,

}
requestBody.SetWorkingHours(workingHours)
isEmailNotificationEnabled := false
requestBody.SetIsEmailNotificationEnabled(&isEmailNotificationEnabled) 
additionalData := map[string]interface{}{
	"role@odata.type" : "#microsoft.graph.bookingStaffRole", 
	"workingHours@odata.type" : "#Collection(microsoft.graph.bookingWorkHours)", 
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.BookingBusinessesById("bookingBusiness-id").StaffMembers().Post(requestBody)


```