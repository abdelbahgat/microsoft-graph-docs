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
identifierUris := []string {
	"https://contosoiwaapp-contoso.msappproxy.net",
}
requestBody.SetIdentifierUris(identifierUris)
web := graphmodels.NewWebApplication()
redirectUris := []string {
	"https://contosoiwaapp-contoso.msappproxy.net",
}
web.SetRedirectUris(redirectUris)
homePageUrl := "https://contosoiwaapp-contoso.msappproxy.net"
web.SetHomePageUrl(&homePageUrl) 
requestBody.SetWeb(web)

applications, err := graphClient.Applications().ByApplicationId("application-id").Patch(context.Background(), requestBody, nil)


```