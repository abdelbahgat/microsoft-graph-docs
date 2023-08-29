---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewChannel()
displayName := "My First Shared Channel"
requestBody.SetDisplayName(&displayName) 
description := "This is my first shared channel"
requestBody.SetDescription(&description) 
membershipType := graphmodels.SHARED_CHANNELMEMBERSHIPTYPE 
requestBody.SetMembershipType(&membershipType) 


conversationMember := graphmodels.NewConversationMember()
"@odata.type" := "#microsoft.graph.aadUserConversationMember"
conversationMember.Set"@odata.type"(&"@odata.type") 
roles := []String {
	"owner",

}
conversationMember.SetRoles(roles)
additionalData := map[string]interface{}{
	"user@odata.bind" : "https://graph.microsoft.com/beta/users('7640023f-fe43-gv3f-9gg4-84a9efe4acd6')", 
}
conversationMember.SetAdditionalData(additionalData)

members := []graphmodels.ConversationMemberable {
	conversationMember,

}
requestBody.SetMembers(members)

result, err := graphClient.TeamsById("team-id").Channels().Post(requestBody)


```