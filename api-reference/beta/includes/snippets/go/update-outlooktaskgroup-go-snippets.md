---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewOutlookTaskGroup()
name := "Personal Tasks"
requestBody.SetName(&name) 

result, err := graphClient.Me().Outlook().TaskGroups().ByTaskGroupId("outlookTaskGroup-id").Patch(context.Background(), requestBody, nil)


```