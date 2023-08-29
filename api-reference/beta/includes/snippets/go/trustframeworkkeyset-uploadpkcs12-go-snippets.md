---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewUploadPkcs12PostRequestBody()
key := "Base64-encoded-pfx-content"
requestBody.SetKey(&key) 
password := "password-value"
requestBody.SetPassword(&password) 

result, err := graphClient.TrustFramework().KeySetsById("trustFrameworkKeySet-id").UploadPkcs12(trustFrameworkKeySet-id).Post(requestBody)


```