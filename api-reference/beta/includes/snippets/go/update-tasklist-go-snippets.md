---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewBaseTaskList()
"@odata.type" := "#microsoft.graph.taskList"
requestBody.Set"@odata.type"(&"@odata.type") 
displayName := "Travel Plan"
requestBody.SetDisplayName(&displayName) 

graphClient.Me().Tasks().ListsById("baseTaskList-id").Patch(requestBody)


```