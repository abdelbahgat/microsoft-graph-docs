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


requestBody := graphmodels.NewB2cAuthenticationMethodsPolicy()
isEmailPasswordAuthenticationEnabled := false
requestBody.SetIsEmailPasswordAuthenticationEnabled(&isEmailPasswordAuthenticationEnabled) 
isUserNameAuthenticationEnabled := true
requestBody.SetIsUserNameAuthenticationEnabled(&isUserNameAuthenticationEnabled) 
isPhoneOneTimePasswordAuthenticationEnabled := true
requestBody.SetIsPhoneOneTimePasswordAuthenticationEnabled(&isPhoneOneTimePasswordAuthenticationEnabled) 

b2cAuthenticationMethodsPolicy, err := graphClient.Policies().B2cAuthenticationMethodsPolicy().Patch(context.Background(), requestBody, nil)


```