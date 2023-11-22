---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewConversationMember()
roles := []string {
	"owner",
}
requestBody.SetRoles(roles)

members, err := graphClient.Teams().ByTeamId("team-id").Channels().ByChannelId("channel-id").Members().ByConversationMemberId("conversationMember-id").Patch(context.Background(), requestBody, nil)


```