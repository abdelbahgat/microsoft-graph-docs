---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewRegistrationPostRequestBody()
additionalData := map[string]interface{}{
	"@odata.type" : "#microsoft.graph.externalMeetingRegistration", 
	"allowedRegistrant" : "everyone", 
}
requestBody.SetAdditionalData(additionalData)

graphClient.Me().OnlineMeetingsById("onlineMeeting-id").Registration().Post(requestBody)


```