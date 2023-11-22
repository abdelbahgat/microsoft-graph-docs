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


requestBody := graphmodels.NewResourceOperation()
resourceName := "Resource Name value"
requestBody.SetResourceName(&resourceName) 
actionName := "Action Name value"
requestBody.SetActionName(&actionName) 
description := "Description value"
requestBody.SetDescription(&description) 

resourceOperations, err := graphClient.DeviceManagement().ResourceOperations().ByResourceOperationId("resourceOperation-id").Patch(context.Background(), requestBody, nil)


```