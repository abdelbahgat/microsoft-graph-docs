---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSetUserPreferredPresencePostRequestBody()
availability := "DoNotDisturb"
requestBody.SetAvailability(&availability) 
activity := "DoNotDisturb"
requestBody.SetActivity(&activity) 
expirationDuration := "PT8H"
requestBody.SetExpirationDuration(&expirationDuration) 

graphClient.UsersById("user-id").Presence().SetUserPreferredPresence(user-id).Post(requestBody)


```