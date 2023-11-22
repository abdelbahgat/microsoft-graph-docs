---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewApplication()
web := graphmodels.NewWebApplication()
redirectUris := []string {
	"https://signin.aws.amazon.com/saml",
}
web.SetRedirectUris(redirectUris)
requestBody.SetWeb(web)
identifierUris := []string {
	"https://signin.aws.amazon.com/saml",
}
requestBody.SetIdentifierUris(identifierUris)

applications, err := graphClient.Applications().ByApplicationId("application-id").Patch(context.Background(), requestBody, nil)


```