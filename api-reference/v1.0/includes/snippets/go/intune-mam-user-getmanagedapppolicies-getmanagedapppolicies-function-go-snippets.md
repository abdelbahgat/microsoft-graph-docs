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



getManagedAppPolicies, err := graphClient.Users().ByUserId("user-id").GetManagedAppPolicies().Get(context.Background(), nil)


```