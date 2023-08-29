---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewDeclinePostRequestBody()
comment := "I won't be able to make this week. How about next week?"
requestBody.SetComment(&comment) 
sendResponse := true
requestBody.SetSendResponse(&sendResponse) 
proposedNewTime := graphmodels.NewTimeSlot()
start := graphmodels.NewDateTimeTimeZone()
dateTime := "2019-12-02T18:00:00"
start.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
start.SetTimeZone(&timeZone) 
proposedNewTime.SetStart(start)
end := graphmodels.NewDateTimeTimeZone()
dateTime := "2019-12-02T19:00:00"
end.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
end.SetTimeZone(&timeZone) 
proposedNewTime.SetEnd(end)
requestBody.SetProposedNewTime(proposedNewTime)

graphClient.Me().EventsById("event-id").Decline(event-id).Post(requestBody)


```