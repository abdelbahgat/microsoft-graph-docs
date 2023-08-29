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
"@odata.type" := "microsoft.graph.educationExcelResource"
resource.Set"@odata.type"(&"@odata.type") 
displayName := "Graph Doc pages.xlsx"
resource.SetDisplayName(&displayName) 
additionalData := map[string]interface{}{
	"fileUrl" : "https://graph.microsoft.com/v1.0/drives/b!OPmUsPgnBUiMIXMxWcj3neC1xck6I5NIsnFxfrLdmXoOOmEQNO79QpIMPdOmY3nf/items/01QTY63RIR7PSV4JJSFJHKNPUVUWGPW4O2", 
}
resource.SetAdditionalData(additionalData)
requestBody.SetResource(resource)

result, err := graphClient.Education().ClassesById("educationClass-id").AssignmentsById("educationAssignment-id").Resources().Post(requestBody)


```