---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewProgramControl()
controlId := "7e59d237-2fb0-4e5d-b7bb-d4f9f9129213"
requestBody.SetControlId(&controlId) 
controlTypeId := "6e4f3d20-c5c3-407f-9695-8460952bcc68"
requestBody.SetControlTypeId(&controlTypeId) 
programId := "7e59d237-2fb0-4e5d-b7bb-d4f9f9129213"
requestBody.SetProgramId(&programId) 

result, err := graphClient.ProgramControls().Post(requestBody)


```