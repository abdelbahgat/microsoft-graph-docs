---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewReplyPostRequestBody()
post := graphmodels.NewPost()
body := graphmodels.NewItemBody()
contentType := graphmodels.TEXT_BODYTYPE 
body.SetContentType(&contentType) 
content := "Which quarter does that file cover? See my attachment."
body.SetContent(&content) 
post.SetBody(body)


attachment := graphmodels.NewAttachment()
"@odata.type" := "#microsoft.graph.fileAttachment"
attachment.Set"@odata.type"(&"@odata.type") 
name := "Another file as attachment"
attachment.SetName(&name) 
additionalData := map[string]interface{}{
	"contentBytes" : "VGhpcyBpcyBhIGZpbGUgdG8gYmUgYXR0YWNoZWQu", 
}
attachment.SetAdditionalData(additionalData)

attachments := []graphmodels.Attachmentable {
	attachment,

}
post.SetAttachments(attachments)
requestBody.SetPost(post)

graphClient.GroupsById("group-id").ThreadsById("conversationThread-id").Reply(group-id, conversationThread-id).Post(requestBody)


```