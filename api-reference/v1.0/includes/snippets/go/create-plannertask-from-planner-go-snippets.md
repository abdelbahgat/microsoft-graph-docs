---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewPlannerTask()
planId := "xqQg5FS2LkCp935s-FIFm2QAFkHM"
requestBody.SetPlanId(&planId) 
bucketId := "hsOf2dhOJkqyYYZEtdzDe2QAIUCR"
requestBody.SetBucketId(&bucketId) 
title := "Update client list"
requestBody.SetTitle(&title) 
assignments := graphmodels.NewPlannerAssignments()
additionalData := map[string]interface{}{
"fbab97d0-4932-4511-b675-204639209557" := graphmodels.NewPlannerAssignment()
orderHint := " !"
"fbab97d0-4932-4511-b675-204639209557".SetOrderHint(&orderHint) 
	assignments.Set"fbab97d0-4932-4511-b675-204639209557"("fbab97d0-4932-4511-b675-204639209557")
}
assignments.SetAdditionalData(additionalData)
requestBody.SetAssignments(assignments)

tasks, err := graphClient.Planner().Tasks().Post(context.Background(), requestBody, nil)


```