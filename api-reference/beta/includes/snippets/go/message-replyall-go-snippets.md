---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewReplyAllPostRequestBody()
message := graphmodels.Newmessage()


attachment := graphmodels.NewAttachment()
"@odata.type" := "#microsoft.graph.fileAttachment"
attachment.Set"@odata.type"(&"@odata.type") 
name := "guidelines.txt"
attachment.SetName(&name) 
additionalData := map[string]interface{}{
	"contentBytes" : "bWFjIGFuZCBjaGVlc2UgdG9kYXk=", 
}
attachment.SetAdditionalData(additionalData)

attachments := []graphmodels.Attachmentable {
	attachment,

}
message.SetAttachments(attachments)
requestBody.SetMessage(message)
comment := "Please take a look at the attached guidelines before you decide on the name."
requestBody.SetComment(&comment) 

graphClient.Me().MessagesById("message-id").ReplyAll(message-id).Post(requestBody)


```