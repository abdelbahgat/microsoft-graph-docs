---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewChecklistItem()
displayName := "Final sign-off from the team"
requestBody.SetDisplayName(&displayName) 

result, err := graphClient.Me().Todo().ListsById("todoTaskList-id").TasksById("todoTask-id").ChecklistItems().Post(requestBody)


```