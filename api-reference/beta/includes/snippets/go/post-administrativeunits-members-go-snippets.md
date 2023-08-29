---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewMembersPostRequestBody()
additionalData := map[string]interface{}{
	"@odata.type" : "#Microsoft.Graph.Group", 
	"description" : "Self help community for golf", 
	"displayName" : "Golf Assist", 
	groupTypes := []String {
		"Unified",

	}
	mailEnabled := true
requestBody.SetMailEnabled(&mailEnabled) 
	"mailNickname" : "golfassist", 
	securityEnabled := false
requestBody.SetSecurityEnabled(&securityEnabled) 
}
requestBody.SetAdditionalData(additionalData)

graphClient.AdministrativeUnitsById("administrativeUnit-id").Members().Post(requestBody)


```