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



itemInsights, err := graphClient.Organization().ByOrganizationId("organization-id").Settings().ItemInsights().Get(context.Background(), nil)


```