---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphidentitygovernance "github.com/microsoftgraph/msgraph-beta-sdk-go/identitygovernance"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphidentitygovernance.IdentityGovernanceAccessReviewsDecisionsFilterByCurrentUser(on='{on}')RequestBuilderGetQueryParameters{
	Expand: [] string {"instance($expand=definition)"},
}
configuration := &graphidentitygovernance.IdentityGovernanceAccessReviewsDecisionsFilterByCurrentUser(on='{on}')RequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

on := "reviewer"
filterByCurrentUser, err := graphClient.IdentityGovernance().AccessReviews().Decisions().FilterByCurrentUserWithOn(&on).Get(context.Background(), configuration)


```