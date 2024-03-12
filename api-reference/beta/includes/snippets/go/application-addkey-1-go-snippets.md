---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/Applications/Item/AddKey"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewAddKeyPostRequestBody()
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

result, err := graphClient.Applications().ByApplicationId("application-id").AddKey().Post(context.Background(), requestBody, nil)


```