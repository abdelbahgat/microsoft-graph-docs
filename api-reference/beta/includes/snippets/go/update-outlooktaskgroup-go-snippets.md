---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewOutlookTaskGroup()
name := "Personal Tasks"
requestBody.SetName(&name) 

graphClient.Me().Outlook().TaskGroupsById("outlookTaskGroup-id").Patch(requestBody)


```