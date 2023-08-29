---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewPasswordCredentialPostRequestBody()
passwordCredential := graphmodels.NewPasswordCredential()
displayName := "Password friendly name"
passwordCredential.SetDisplayName(&displayName) 
requestBody.SetPasswordCredential(passwordCredential)

result, err := graphClient.ApplicationsById("application-id").AddPassword(application-id).Post(requestBody)


```