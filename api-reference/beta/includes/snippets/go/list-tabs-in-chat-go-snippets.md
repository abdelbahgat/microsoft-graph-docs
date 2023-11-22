---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphchats "github.com/microsoftgraph/msgraph-beta-sdk-go/chats"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphchats.ChatItemTabsRequestBuilderGetQueryParameters{
	Expand: [] string {"teamsApp"},
}
configuration := &graphchats.ChatItemTabsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

tabs, err := graphClient.Chats().ByChatId("chat-id").Tabs().Get(context.Background(), configuration)


```