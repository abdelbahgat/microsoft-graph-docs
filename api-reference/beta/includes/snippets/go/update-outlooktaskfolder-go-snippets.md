---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewOutlookTaskFolder()
name := "Charity work"
requestBody.SetName(&name) 

graphClient.Me().Outlook().TaskFoldersById("outlookTaskFolder-id").Patch(requestBody)


```