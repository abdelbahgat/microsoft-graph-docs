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


requestBody := graphmodels.NewUser()
accountEnabled := true
requestBody.SetAccountEnabled(&accountEnabled) 
displayName := "Adele Vance"
requestBody.SetDisplayName(&displayName) 
mailNickname := "AdeleV"
requestBody.SetMailNickname(&mailNickname) 
userPrincipalName := "AdeleV@contoso.onmicrosoft.com"
requestBody.SetUserPrincipalName(&userPrincipalName) 
passwordProfile := graphmodels.NewPasswordProfile()
forceChangePasswordNextSignIn := true
passwordProfile.SetForceChangePasswordNextSignIn(&forceChangePasswordNextSignIn) 
password := "xWwvJ]6NMw+bWH-d"
passwordProfile.SetPassword(&password) 
requestBody.SetPasswordProfile(passwordProfile)

users, err := graphClient.Users().Post(context.Background(), requestBody, nil)


```