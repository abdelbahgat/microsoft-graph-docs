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


requestBody := graphmodels.NewOAuth2PermissionGrant()
clientId := "ef969797-201d-4f6b-960c-e9ed5f31dab5"
requestBody.SetClientId(&clientId) 
consentType := "AllPrincipals"
requestBody.SetConsentType(&consentType) 
resourceId := "943603e4-e787-4fe9-93d1-e30f749aae39"
requestBody.SetResourceId(&resourceId) 
scope := "DelegatedPermissionGrant.ReadWrite.All"
requestBody.SetScope(&scope) 

oauth2PermissionGrants, err := graphClient.Oauth2PermissionGrants().Post(context.Background(), requestBody, nil)


```