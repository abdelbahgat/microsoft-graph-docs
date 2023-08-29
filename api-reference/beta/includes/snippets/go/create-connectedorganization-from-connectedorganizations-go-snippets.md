---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewConnectedOrganization()
displayName := "Connected organization name"
requestBody.SetDisplayName(&displayName) 
description := "Connected organization description"
requestBody.SetDescription(&description) 


identitySource := graphmodels.NewIdentitySource()
"@odata.type" := "#microsoft.graph.domainIdentitySource"
identitySource.Set"@odata.type"(&"@odata.type") 
additionalData := map[string]interface{}{
	"domainName" : "example.com", 
	"displayName" : "example.com", 
}
identitySource.SetAdditionalData(additionalData)

identitySources := []graphmodels.IdentitySourceable {
	identitySource,

}
requestBody.SetIdentitySources(identitySources)
state := graphmodels.PROPOSED_CONNECTEDORGANIZATIONSTATE 
requestBody.SetState(&state) 

result, err := graphClient.IdentityGovernance().EntitlementManagement().ConnectedOrganizations().Post(requestBody)


```