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



timeOffRequests, err := graphClient.Teams().ByTeamId("team-id").Schedule().TimeOffRequests().ByTimeOffRequestId("timeOffRequest-id").Get(context.Background(), nil)


```