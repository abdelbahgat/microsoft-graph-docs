---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewChatMessage()
subject := null
requestBody.SetSubject(&subject) 
body := graphmodels.NewItemBody()
contentType := graphmodels.HTML_BODYTYPE 
body.SetContentType(&contentType) 
content := "<attachment id=\"74d20c7f34aa4a7fb74e2b30004247c5\"></attachment>"
body.SetContent(&content) 
requestBody.SetBody(body)


chatMessageAttachment := graphmodels.NewChatMessageAttachment()
id := "74d20c7f34aa4a7fb74e2b30004247c5"
chatMessageAttachment.SetId(&id) 
contentType := "application/vnd.microsoft.card.thumbnail"
chatMessageAttachment.SetContentType(&contentType) 
contentUrl := null
chatMessageAttachment.SetContentUrl(&contentUrl) 
content := "{\r\n  \"title\": \"This is an example of posting a card\",\r\n  \"subtitle\": \"<h3>This is the subtitle</h3>\",\r\n  \"text\": \"Here is some body text. <br>\r\nAnd a <a href=\\"http://microsoft.com/\\">hyperlink</a>. <br>\r\nAnd below that is some buttons:\",\r\n  \"buttons\": [\r\n    {\r\n      \"type\": \"messageBack\",\r\n      \"title\": \"Login to FakeBot\",\r\n      \"text\": \"login\",\r\n      \"displayText\": \"login\",\r\n      \"value\": \"login\"\r\n    }\r\n  ]\r\n}"
chatMessageAttachment.SetContent(&content) 
name := null
chatMessageAttachment.SetName(&name) 
thumbnailUrl := null
chatMessageAttachment.SetThumbnailUrl(&thumbnailUrl) 

attachments := []graphmodels.ChatMessageAttachmentable {
	chatMessageAttachment,

}
requestBody.SetAttachments(attachments)

result, err := graphClient.TeamsById("team-id").ChannelsById("channel-id").Messages().Post(requestBody)


```