---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



resourceOperations, err := graphClient.DeviceManagement().ResourceOperations().ByResourceOperationId("resourceOperation-id").Get(context.Background(), nil)


```