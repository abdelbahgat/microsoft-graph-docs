---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewPermission()
roles := []String {
	"write",

}
requestBody.SetRoles(roles)


identitySet := graphmodels.NewIdentitySet()
application := graphmodels.NewIdentity()
id := "89ea5c94-7736-4e25-95ad-3fa95f62b66e"
application.SetId(&id) 
displayName := "Contoso Time Manager App"
application.SetDisplayName(&displayName) 
identitySet.SetApplication(application)

grantedToIdentities := []graphmodels.IdentitySetable {
	identitySet,

}
requestBody.SetGrantedToIdentities(grantedToIdentities)

result, err := graphClient.SitesById("site-id").Permissions().Post(requestBody)


```