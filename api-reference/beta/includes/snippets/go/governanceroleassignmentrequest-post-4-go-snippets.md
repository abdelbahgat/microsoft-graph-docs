---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewGovernanceRoleAssignmentRequest()
roleDefinitionId := "65bb4622-61f5-4f25-9d75-d0e20cf92019"
requestBody.SetRoleDefinitionId(&roleDefinitionId) 
resourceId := "e5e7d29d-5465-45ac-885f-4716a5ee74b5"
requestBody.SetResourceId(&resourceId) 
subjectId := "74765671-9ca4-40d7-9e36-2f4a570608a6"
requestBody.SetSubjectId(&subjectId) 
assignmentState := "Eligible"
requestBody.SetAssignmentState(&assignmentState) 
type := "AdminRemove"
requestBody.SetType(&type) 

result, err := graphClient.PrivilegedAccessById("privilegedAccess-id").RoleAssignmentRequests().Post(requestBody)


```