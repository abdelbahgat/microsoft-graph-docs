---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewConfirmCompromisedPostRequestBody()
servicePrincipalIds := []String {
	"9089a539-a539-9089-39a5-899039a58990",

}
requestBody.SetServicePrincipalIds(servicePrincipalIds)

graphClient.IdentityProtection().RiskyServicePrincipals().ConfirmCompromised().Post(requestBody)


```