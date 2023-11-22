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


requestBody := graphmodels.NewGroup()
description := "Marketing group"
requestBody.SetDescription(&description) 
displayName := "Marketing resources"
requestBody.SetDisplayName(&displayName) 
mailEnabled := false
requestBody.SetMailEnabled(&mailEnabled) 
mailNickname := "markres"
requestBody.SetMailNickname(&mailNickname) 
securityEnabled := true
requestBody.SetSecurityEnabled(&securityEnabled) 

groups, err := graphClient.Groups().Post(context.Background(), requestBody, nil)


```