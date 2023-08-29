---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewIdentityProviderBase()
"@odata.type" := "microsoft.graph.openIdConnectIdentityProvider"
requestBody.Set"@odata.type"(&"@odata.type") 
displayName := "Login with the Contoso identity provider"
requestBody.SetDisplayName(&displayName) 
additionalData := map[string]interface{}{
	"clientId" : "56433757-cadd-4135-8431-2c9e3fd68ae8", 
	"clientSecret" : "12345", 
claimsMapping := graphmodels.New()
userId := "myUserId"
claimsMapping.SetUserId(&userId) 
givenName := "myGivenName"
claimsMapping.SetGivenName(&givenName) 
surname := "mySurname"
claimsMapping.SetSurname(&surname) 
email := "myEmail"
claimsMapping.SetEmail(&email) 
displayName := "myDisplayName"
claimsMapping.SetDisplayName(&displayName) 
	requestBody.SetClaimsMapping(claimsMapping)
	"domainHint" : "mycustomoidc", 
	"metadataUrl" : "https://mycustomoidc.com/.well-known/openid-configuration", 
	"responseMode" : "form_post", 
	"responseType" : "code", 
	"scope" : "openid", 
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.Identity().IdentityProviders().Post(requestBody)


```