---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewKeyCredentialPostRequestBody()
keyCredential := graphmodels.NewKeyCredential()
type := "AsymmetricX509Cert"
keyCredential.SetType(&type) 
usage := "Verify"
keyCredential.SetUsage(&usage) 
key := []byte("mIIDYDCCAki...")
keyCredential.SetKey(&key) 
requestBody.SetKeyCredential(keyCredential)
passwordCredential := null
requestBody.SetPasswordCredential(&passwordCredential) 
proof := "eyJ0eXAiOiJ..."
requestBody.SetProof(&proof) 

result, err := graphClient.ServicePrincipalsById("servicePrincipal-id").AddKey(servicePrincipal-id).Post(requestBody)


```