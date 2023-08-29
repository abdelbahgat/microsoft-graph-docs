---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSubjectRightsRequest()
type := graphmodels.SUBJECTRIGHTSREQUESTTYPE_GRAPH_MICROSOFT_SUBJECTRIGHTSREQUESTTYPE 
requestBody.SetType(&type) 
dataSubjectType := graphmodels.DATASUBJECTTYPE_GRAPH_MICROSOFT_DATASUBJECTTYPE 
requestBody.SetDataSubjectType(&dataSubjectType) 
regulations := []String {
	"String",

}
requestBody.SetRegulations(regulations)
displayName := "String"
requestBody.SetDisplayName(&displayName) 
description := "String"
requestBody.SetDescription(&description) 
internalDueDateTime , err := time.Parse(time.RFC3339, "String (timestamp)")
requestBody.SetInternalDueDateTime(&internalDueDateTime) 
dataSubject := graphmodels.NewDataSubject()
firstName := "String"
dataSubject.SetFirstName(&firstName) 
lastName := "String"
dataSubject.SetLastName(&lastName) 
email := "String"
dataSubject.SetEmail(&email) 
residency := "String"
dataSubject.SetResidency(&residency) 
additionalData := map[string]interface{}{
	"phoneNumber" : "String", 
	"sSN" : "String", 
}
dataSubject.SetAdditionalData(additionalData)
requestBody.SetDataSubject(dataSubject)

result, err := graphClient.Privacy().SubjectRightsRequests().Post(requestBody)


```