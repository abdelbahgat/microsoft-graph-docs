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



sets, err := graphClient.Sites().BySiteId("site-id").TermStore().Groups().ByGroupId("group-id").Sets().Get(context.Background(), nil)


```