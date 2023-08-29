---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewPlannerTask()
planId := "xqQg5FS2LkCp935s-FIFm2QAFkHM"
requestBody.SetPlanId(&planId) 
bucketId := "hsOf2dhOJkqyYYZEtdzDe2QAIUCR"
requestBody.SetBucketId(&bucketId) 
title := "Update client list"
requestBody.SetTitle(&title) 
assignments := graphmodels.NewPlannerAssignments()
additionalData := map[string]interface{}{
"fbab97d0-4932-4511-b675-204639209557" := graphmodels.New()
"@odata.type" := "#microsoft.graph.plannerAssignment"
"fbab97d0-4932-4511-b675-204639209557".Set"@odata.type"(&"@odata.type") 
orderHint := " !"
"fbab97d0-4932-4511-b675-204639209557".SetOrderHint(&orderHint) 
	assignments.Set"fbab97d0-4932-4511-b675-204639209557"("fbab97d0-4932-4511-b675-204639209557")
}
assignments.SetAdditionalData(additionalData)
requestBody.SetAssignments(assignments)

result, err := graphClient.Planner().Tasks().Post(requestBody)


```