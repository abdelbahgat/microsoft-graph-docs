---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"Prefer": "return=representation",
}
configuration := &graphconfig.TimeOffReasonRequestBuilderPutRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewTimeOffReason()
additionalData := map[string]interface{}{
	"displayName" : "Vacation", 
	"iconType" : "plane", 
	isActive := true
requestBody.SetIsActive(&isActive) 
}
requestBody.SetAdditionalData(additionalData)

graphClient.TeamsById("team-id").Schedule().TimeOffReasonsById("timeOffReason-id").PutWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```