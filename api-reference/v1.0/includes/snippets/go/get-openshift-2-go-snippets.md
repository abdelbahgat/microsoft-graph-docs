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



openShifts, err := graphClient.Teams().ByTeamId("team-id").Schedule().OpenShifts().Get(context.Background(), nil)


```