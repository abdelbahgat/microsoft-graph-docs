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



getAllMessages, err := graphClient.Teamwork().DeletedTeams().ByDeletedTeamId("deletedTeam-id").Channels().GetAllMessages().Get(context.Background(), nil)


```