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



onlineMeetings, err := graphClient.Me().OnlineMeetings().ByOnlineMeetingId("onlineMeeting-id").Get(context.Background(), nil)


```