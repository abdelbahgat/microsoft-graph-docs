---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewEducationAssignment()
dueDateTime , err := time.Parse(time.RFC3339, "2021-09-07T00:00:00Z")
requestBody.SetDueDateTime(&dueDateTime) 
displayName := "Reading test 09.03 #4"
requestBody.SetDisplayName(&displayName) 
instructions := graphmodels.NewEducationItemBody()
contentType := graphmodels.TEXT_BODYTYPE 
instructions.SetContentType(&contentType) 
content := "Read chapter 4"
instructions.SetContent(&content) 
requestBody.SetInstructions(instructions)
grading := graphmodels.NewEducationAssignmentGradeType()
"@odata.type" := "#microsoft.graph.educationAssignmentGradeType"
grading.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"maxPoints" : int32(50) , 
}
grading.SetAdditionalData(additionalData)
requestBody.SetGrading(grading)
assignTo := graphmodels.NewEducationAssignmentRecipient()
"@odata.type" := "#microsoft.graph.educationAssignmentGradeType"
assignTo.Set"@odata.type"(&"@odata.type") 
requestBody.SetAssignTo(assignTo)
status := graphmodels.DRAFT_EDUCATIONASSIGNMENTSTATUS 
requestBody.SetStatus(&status) 
allowStudentsToAddResourcesToSubmission := true
requestBody.SetAllowStudentsToAddResourcesToSubmission(&allowStudentsToAddResourcesToSubmission) 

result, err := graphClient.Education().ClassesById("educationClass-id").Assignments().Post(requestBody)


```