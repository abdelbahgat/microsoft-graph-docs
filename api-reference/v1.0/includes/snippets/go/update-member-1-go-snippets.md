---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewConversationMember()
"@odata.type" := "#microsoft.graph.aadUserConversationMember"
requestBody.Set"@odata.type"(&"@odata.type") 
roles := []String {
	"owner",

}
requestBody.SetRoles(roles)

graphClient.TeamsById("team-id").ChannelsById("channel-id").MembersById("conversationMember-id").Patch(requestBody)


```