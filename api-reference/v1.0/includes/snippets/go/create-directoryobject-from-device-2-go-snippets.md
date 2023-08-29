---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewRegisteredUser()
additionalData := map[string]interface{}{
	"@odata.id" : "https://graph.microsoft.com/v1.0/directoryObjects/{id}", 
}
requestBody.SetAdditionalData(additionalData)

graphClient.DevicesById("device-id").RegisteredUsersById("directoryObject-id").Post(requestBody)


```