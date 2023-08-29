---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewUnifiedRoleAssignment()
"@odata.type" := "#microsoft.graph.unifiedRoleAssignment"
requestBody.Set"@odata.type"(&"@odata.type") 
roleDefinitionId := "58a13ea3-c632-46ae-9ee0-9c0d43cd7f3d"
requestBody.SetRoleDefinitionId(&roleDefinitionId) 
principalId := "f8ca5a85-489a-49a0-b555-0a6d81e56f0d"
requestBody.SetPrincipalId(&principalId) 
directoryScopeId := "/attributeSets/Engineering"
requestBody.SetDirectoryScopeId(&directoryScopeId) 

result, err := graphClient.RoleManagement().Directory().RoleAssignments().Post(requestBody)


```