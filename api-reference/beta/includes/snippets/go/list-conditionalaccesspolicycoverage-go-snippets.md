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



conditionalAccessPolicyCoverages, err := graphClient.TenantRelationships().ManagedTenants().ConditionalAccessPolicyCoverages().Get(context.Background(), nil)


```