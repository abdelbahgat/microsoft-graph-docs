---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-beta-sdk-go/Chats/Item/MarkChatReadForUser"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewMarkChatReadForUserPostRequestBody()
user := graphmodels.NewTeamworkUserIdentity()
id := "d864e79f-a516-4d0f-9fee-0eeb4d61fdc2"
user.SetId(&id) 
additionalData := map[string]interface{}{
	"tenantId" : "2a690434-97d9-4eed-83a6-f5f13600199a", 
}
user.SetAdditionalData(additionalData)
requestBody.SetUser(user)

graphClient.Chats().ByChatId("chat-id").MarkChatReadForUser().Post(context.Background(), requestBody, nil)


```