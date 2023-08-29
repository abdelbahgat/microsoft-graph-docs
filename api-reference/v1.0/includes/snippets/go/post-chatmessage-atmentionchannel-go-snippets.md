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
content := "<div><div><at id=\"0\">General</at>&nbsp;Hello there!</div></div>"
body.SetContent(&content) 
requestBody.SetBody(body)


chatMessageMention := graphmodels.NewChatMessageMention()
id := int32(0)
chatMessageMention.SetId(&id) 
mentionText := "General"
chatMessageMention.SetMentionText(&mentionText) 
mentioned := graphmodels.Newmentioned()
conversation := graphmodels.Newconversation()
id := "19:0b50940236084d258c97b21bd01917b0@thread.skype"
conversation.SetId(&id) 
displayName := "General"
conversation.SetDisplayName(&displayName) 
conversationIdentityType := graphmodels.CHANNEL_TEAMWORKCONVERSATIONIDENTITYTYPE 
conversation.SetConversationIdentityType(&conversationIdentityType) 
mentioned.SetConversation(conversation)
chatMessageMention.SetMentioned(mentioned)

mentions := []graphmodels.ChatMessageMentionable {
	chatMessageMention,

}
requestBody.SetMentions(mentions)

result, err := graphClient.TeamsById("team-id").ChannelsById("channel-id").Messages().Post(requestBody)


```