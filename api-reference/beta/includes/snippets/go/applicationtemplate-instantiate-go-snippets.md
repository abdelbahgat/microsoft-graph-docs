---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/ApplicationTemplates/Item/Instantiate"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewInstantiatePostRequestBody()
displayName := "testProperties"
requestBody.SetDisplayName(&displayName) 

result, err := graphClient.ApplicationTemplates().ByApplicationTemplateId("applicationTemplate-id").Instantiate().Post(context.Background(), requestBody, nil)


```