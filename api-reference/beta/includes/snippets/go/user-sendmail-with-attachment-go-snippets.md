---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSendMailPostRequestBody()
message := graphmodels.NewMessage()
subject := "Meet for lunch?"
message.SetSubject(&subject) 
body := graphmodels.NewItemBody()
contentType := graphmodels.TEXT_BODYTYPE 
body.SetContentType(&contentType) 
content := "The new cafeteria is open."
body.SetContent(&content) 
message.SetBody(body)


recipient := graphmodels.NewRecipient()
emailAddress := graphmodels.NewEmailAddress()
address := "meganb@contoso.onmicrosoft.com"
emailAddress.SetAddress(&address) 
recipient.SetEmailAddress(emailAddress)

toRecipients := []graphmodels.Recipientable {
	recipient,

}
message.SetToRecipients(toRecipients)


attachment := graphmodels.NewAttachment()
"@odata.type" := "#microsoft.graph.fileAttachment"
attachment.Set"@odata.type"(&"@odata.type") 
name := "attachment.txt"
attachment.SetName(&name) 
contentType := "text/plain"
attachment.SetContentType(&contentType) 
additionalData := map[string]interface{}{
	"contentBytes" : "SGVsbG8gV29ybGQh", 
}
attachment.SetAdditionalData(additionalData)

attachments := []graphmodels.Attachmentable {
	attachment,

}
message.SetAttachments(attachments)
requestBody.SetMessage(message)

graphClient.Me().SendMail().Post(requestBody)


```