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



on := "reviewer"
filterByCurrentUser, err := graphClient.IdentityGovernance().AccessReviews().Definitions().ByAccessReviewScheduleDefinitionId("accessReviewScheduleDefinition-id").Instances().FilterByCurrentUserWithOn(&on).Get(context.Background(), nil)


```