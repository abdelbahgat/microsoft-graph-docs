---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewChatMessage()
body := graphmodels.NewItemBody()
contentType := graphmodels.HTML_BODYTYPE 
body.SetContentType(&contentType) 
content := "<div><div><at id=\"0\">GraphTesting</at>&nbsp;Hello team</div></div>"
body.SetContent(&content) 
requestBody.SetBody(body)


chatMessageMention := graphmodels.NewChatMessageMention()
id := int32(0)
chatMessageMention.SetId(&id) 
mentionText := "GraphTesting"
chatMessageMention.SetMentionText(&mentionText) 
mentioned := graphmodels.Newmentioned()
conversation := graphmodels.Newconversation()
id := "68a3e365-f7d9-4a56-b499-24332a9cc572"
conversation.SetId(&id) 
displayName := "GraphTesting"
conversation.SetDisplayName(&displayName) 
conversationIdentityType := graphmodels.TEAM_TEAMWORKCONVERSATIONIDENTITYTYPE 
conversation.SetConversationIdentityType(&conversationIdentityType) 
mentioned.SetConversation(conversation)
chatMessageMention.SetMentioned(mentioned)

mentions := []graphmodels.ChatMessageMentionable {
	chatMessageMention,

}
requestBody.SetMentions(mentions)
reactions := []graphmodels.ChatMessageReactionable {

}
requestBody.SetReactions(reactions)

result, err := graphClient.TeamsById("team-id").ChannelsById("channel-id").Messages().Post(requestBody)


```