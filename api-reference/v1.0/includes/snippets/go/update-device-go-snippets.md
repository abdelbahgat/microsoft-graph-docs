---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewDevice()
accountEnabled := false
requestBody.SetAccountEnabled(&accountEnabled) 

graphClient.DevicesById("device-id").Patch(requestBody)


```