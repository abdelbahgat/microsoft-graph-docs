---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewChangeDeploymentStatusPostRequestBody()
tenantGroupId := "String"
requestBody.SetTenantGroupId(&tenantGroupId) 
tenantId := "String"
requestBody.SetTenantId(&tenantId) 
managementActionId := "String"
requestBody.SetManagementActionId(&managementActionId) 
managementTemplateId := "String"
requestBody.SetManagementTemplateId(&managementTemplateId) 
status := "String"
requestBody.SetStatus(&status) 

result, err := graphClient.TenantRelationships().ManagedTenants().ManagementActionTenantDeploymentStatuses().ChangeDeploymentStatus().Post(requestBody)


```