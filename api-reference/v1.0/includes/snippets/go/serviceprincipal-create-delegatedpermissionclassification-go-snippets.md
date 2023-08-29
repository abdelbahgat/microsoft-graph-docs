---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewDelegatedPermissionClassification()
permissionId := "e1fe6dd8-ba31-4d61-89e7-88639da4683d"
requestBody.SetPermissionId(&permissionId) 
permissionName := "User.Read"
requestBody.SetPermissionName(&permissionName) 
classification := graphmodels.LOW_PERMISSIONCLASSIFICATIONTYPE 
requestBody.SetClassification(&classification) 

result, err := graphClient.ServicePrincipalsById("servicePrincipal-id").DelegatedPermissionClassifications().Post(requestBody)


```