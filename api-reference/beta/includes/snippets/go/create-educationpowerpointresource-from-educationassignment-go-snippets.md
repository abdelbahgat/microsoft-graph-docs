---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewEducationAssignmentResource()
distributeForStudentWork := false
requestBody.SetDistributeForStudentWork(&distributeForStudentWork) 
resource := graphmodels.NewEducationResource()
"@odata.type" := "microsoft.graph.educationPowerPointResource"
resource.Set"@odata.type"(&"@odata.type") 
displayName := "state diagram.pptx"
resource.SetDisplayName(&displayName) 
additionalData := map[string]interface{}{
	"fileUrl" : "https://graph.microsoft.com/beta/drives/b!OPmUsPgnBUiMIXMxWcj3neC1xck6I5NIsnFxfrLdmXoOOmEQNO79QpIMPdOmY3nf/items/01QTY63RN327OXRN6EVFE2Q5FRJZTN5EOJ", 
}
resource.SetAdditionalData(additionalData)
requestBody.SetResource(resource)

result, err := graphClient.Education().ClassesById("educationClass-id").AssignmentsById("educationAssignment-id").Resources().Post(requestBody)


```