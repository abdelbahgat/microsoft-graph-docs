---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAppManagementPolicie()
additionalData := map[string]interface{}{
	"@odata.id" : "https://graph.microsoft.com/beta/policies/appManagementPolicies/{id}", 
}
requestBody.SetAdditionalData(additionalData)

graphClient.ServicePrincipalsById("servicePrincipal-id").AppManagementPoliciesById("appManagementPolicy-id").Post(requestBody)


```