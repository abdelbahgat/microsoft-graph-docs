---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAccessPackageResourceRequest()
catalogId := "beedadfe-01d5-4025-910b-84abb9369997"
requestBody.SetCatalogId(&catalogId) 
requestType := "AdminAdd"
requestBody.SetRequestType(&requestType) 
accessPackageResource := graphmodels.NewaccessPackageResource()
originId := "c6294667-7348-4f5a-be73-9d2c65f574f3"
accessPackageResource.SetOriginId(&originId) 
originSystem := "AadGroup"
accessPackageResource.SetOriginSystem(&originSystem) 
requestBody.SetAccessPackageResource(accessPackageResource)

result, err := graphClient.IdentityGovernance().EntitlementManagement().AccessPackageResourceRequests().Post(requestBody)


```