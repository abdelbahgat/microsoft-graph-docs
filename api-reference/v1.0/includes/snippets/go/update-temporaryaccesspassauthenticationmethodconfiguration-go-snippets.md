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


requestBody := graphmodels.NewAuthenticationMethodConfiguration()
isUsableOnce := true
requestBody.SetIsUsableOnce(&isUsableOnce) 

authenticationMethodConfigurations, err := graphClient.Policies().AuthenticationMethodsPolicy().AuthenticationMethodConfigurations().ByAuthenticationMethodConfigurationId("authenticationMethodConfiguration-id").Patch(context.Background(), requestBody, nil)


```