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



threads, err := graphClient.Groups().ByGroupId("group-id").Conversations().ByConversationId("conversation-id").Threads().Get(context.Background(), nil)


```