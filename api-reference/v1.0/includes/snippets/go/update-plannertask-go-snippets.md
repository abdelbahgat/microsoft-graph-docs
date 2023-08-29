---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"Prefer": "return=representation",
	"If-Match": "W/\"JzEtVGFzayAgQEBAQEBAQEBAQEBAQEBAWCc=\"",
}
configuration := &graphconfig.PlannerTaskRequestBuilderPatchRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewPlannerTask()
assignments := graphmodels.NewPlannerAssignments()
additionalData := map[string]interface{}{
"fbab97d0-4932-4511-b675-204639209557" := graphmodels.New()
"@odata.type" := "#microsoft.graph.plannerAssignment"
"fbab97d0-4932-4511-b675-204639209557".Set"@odata.type"(&"@odata.type") 
orderHint := "N9917 U2883!"
"fbab97d0-4932-4511-b675-204639209557".SetOrderHint(&orderHint) 
	assignments.Set"fbab97d0-4932-4511-b675-204639209557"("fbab97d0-4932-4511-b675-204639209557")
}
assignments.SetAdditionalData(additionalData)
requestBody.SetAssignments(assignments)
appliedCategories := graphmodels.NewPlannerAppliedCategories()
additionalData := map[string]interface{}{
	category3 := true
appliedCategories.SetCategory3(&category3) 
	category4 := false
appliedCategories.SetCategory4(&category4) 
}
appliedCategories.SetAdditionalData(additionalData)
requestBody.SetAppliedCategories(appliedCategories)

graphClient.Planner().TasksById("plannerTask-id").PatchWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```