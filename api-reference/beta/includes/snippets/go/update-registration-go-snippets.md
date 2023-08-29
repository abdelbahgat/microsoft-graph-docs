---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewMeetingRegistration()
subject := "Microsoft Ignite: Day 1"
requestBody.SetSubject(&subject) 
startDateTime , err := time.Parse(time.RFC3339, "2021-11-02T08:00:00-08:00")
requestBody.SetStartDateTime(&startDateTime) 
endDateTime , err := time.Parse(time.RFC3339, "2021-11-02T15:45:00-08:00")
requestBody.SetEndDateTime(&endDateTime) 


meetingSpeaker := graphmodels.NewMeetingSpeaker()
displayName := "Henry Ross"
meetingSpeaker.SetDisplayName(&displayName) 
bio := "Chairman and Chief Executive Officer"
meetingSpeaker.SetBio(&bio) 
meetingSpeaker1 := graphmodels.NewMeetingSpeaker()
displayName := "Fred Ryan"
meetingSpeaker1.SetDisplayName(&displayName) 
bio := "CVP"
meetingSpeaker1.SetBio(&bio) 

speakers := []graphmodels.MeetingSpeakerable {
	meetingSpeaker,
	meetingSpeaker1,

}
requestBody.SetSpeakers(speakers)

graphClient.Me().OnlineMeetingsById("onlineMeeting-id").Registration().Patch(requestBody)


```