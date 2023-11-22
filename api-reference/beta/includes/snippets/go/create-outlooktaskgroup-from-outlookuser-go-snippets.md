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


requestBody := graphmodels.NewOutlookTaskGroup()
name := "Leisure tasks"
requestBody.SetName(&name) 

taskGroups, err := graphClient.Me().Outlook().TaskGroups().Post(context.Background(), requestBody, nil)


```