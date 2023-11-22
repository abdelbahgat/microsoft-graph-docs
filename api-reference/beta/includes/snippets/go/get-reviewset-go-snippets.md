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



reviewSets, err := graphClient.Compliance().Ediscovery().Cases().ByCaseId("case-id").ReviewSets().ByReviewSetId("reviewSet-id").Get(context.Background(), nil)


```