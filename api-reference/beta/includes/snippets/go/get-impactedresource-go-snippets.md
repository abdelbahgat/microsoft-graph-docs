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



impactedResources, err := graphClient.Directory().Recommendations().ByRecommendationId("recommendation-id").ImpactedResources().ByImpactedResourceId("impactedResource-id").Get(context.Background(), nil)


```