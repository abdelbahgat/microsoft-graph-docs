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



educationalActivities, err := graphClient.Me().Profile().EducationalActivities().ByEducationalActivityId("educationalActivity-id").Get(context.Background(), nil)


```