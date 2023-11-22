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



aggregatedPolicyCompliances, err := graphClient.TenantRelationships().ManagedTenants().AggregatedPolicyCompliances().Get(context.Background(), nil)


```