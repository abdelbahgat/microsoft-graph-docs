---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



subscribedSkus, err := graphClient.SubscribedSkus().BySubscribedSkuId("subscribedSku-id").Get(context.Background(), nil)


```