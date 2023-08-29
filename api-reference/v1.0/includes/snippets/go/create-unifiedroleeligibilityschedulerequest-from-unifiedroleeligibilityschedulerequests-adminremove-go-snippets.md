---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewUnifiedRoleEligibilityScheduleRequest()
action := "adminRemove"
requestBody.SetAction(&action) 
roleDefinitionId := "8424c6f0-a189-499e-bbd0-26c1753c96d4"
requestBody.SetRoleDefinitionId(&roleDefinitionId) 
directoryScopeId := "/"
requestBody.SetDirectoryScopeId(&directoryScopeId) 
principalId := "071cc716-8147-4397-a5ba-b2105951cc0b"
requestBody.SetPrincipalId(&principalId) 

result, err := graphClient.RoleManagement().Directory().RoleEligibilityScheduleRequests().Post(requestBody)


```