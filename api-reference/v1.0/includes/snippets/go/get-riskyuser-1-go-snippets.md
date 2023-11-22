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



riskyUsers, err := graphClient.IdentityProtection().RiskyUsers().ByRiskyUserId("riskyUser-id").Get(context.Background(), nil)


```