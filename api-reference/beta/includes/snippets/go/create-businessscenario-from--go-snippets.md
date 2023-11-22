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


requestBody := graphmodels.NewBusinessScenario()
displayName := "Contoso Order Tracking"
requestBody.SetDisplayName(&displayName) 
uniqueName := "com.contoso.apps.ordertracking"
requestBody.SetUniqueName(&uniqueName) 

businessScenarios, err := graphClient.Solutions().BusinessScenarios().Post(context.Background(), requestBody, nil)


```