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



customTaskExtensions, err := graphClient.IdentityGovernance().LifecycleWorkflows().CustomTaskExtensions().Get(context.Background(), nil)


```