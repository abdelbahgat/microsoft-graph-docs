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



graphClient.Applications().ByApplicationId("application-id").TokenLifetimePolicies().ByTokenLifetimePolicyId("tokenLifetimePolicy-id").Ref().Delete(context.Background(), nil)


```