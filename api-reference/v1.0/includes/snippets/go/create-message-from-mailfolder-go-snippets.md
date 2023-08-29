---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewMessage()
receivedDateTime , err := time.Parse(time.RFC3339, "datetime-value")
requestBody.SetReceivedDateTime(&receivedDateTime) 
sentDateTime , err := time.Parse(time.RFC3339, "datetime-value")
requestBody.SetSentDateTime(&sentDateTime) 
hasAttachments := true
requestBody.SetHasAttachments(&hasAttachments) 
subject := "subject-value"
requestBody.SetSubject(&subject) 
body := graphmodels.NewItemBody()
content := "content-value"
body.SetContent(&content) 
requestBody.SetBody(body)
bodyPreview := "bodyPreview-value"
requestBody.SetBodyPreview(&bodyPreview) 

result, err := graphClient.Me().MailFoldersById("mailFolder-id").Messages().Post(requestBody)


```