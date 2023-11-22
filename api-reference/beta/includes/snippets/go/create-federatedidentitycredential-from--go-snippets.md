---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewFederatedIdentityCredential()
name := "testing02"
requestBody.SetName(&name) 
issuer := "https://login.microsoftonline.com/3d1e2be9-a10a-4a0c-8380-7ce190f98ed9/v2.0"
requestBody.SetIssuer(&issuer) 
subject := "a7d388c3-5e3f-4959-ac7d-786b3383006a"
requestBody.SetSubject(&subject) 
audiences := []string {
	"api://AzureADTokenExchange",
}
requestBody.SetAudiences(audiences)

federatedIdentityCredentials, err := graphClient.Applications().ByApplicationId("application-id").FederatedIdentityCredentials().Post(context.Background(), requestBody, nil)


```