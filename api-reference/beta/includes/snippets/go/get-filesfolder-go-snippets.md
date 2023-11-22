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



filesFolder, err := graphClient.Teams().ByTeamId("team-id").Channels().ByChannelId("channel-id").FilesFolder().Get(context.Background(), nil)


```