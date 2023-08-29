---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAttachment()
"@odata.type" := "#microsoft.graph.itemAttachment"
requestBody.Set"@odata.type"(&"@odata.type") 
name := "Holiday event"
requestBody.SetName(&name) 
additionalData := map[string]interface{}{
item := graphmodels.New()
"@odata.type" := "microsoft.graph.event"
item.Set"@odata.type"(&"@odata.type") 
subject := "Discuss gifts for children"
item.SetSubject(&subject) 
body := graphmodels.New()
contentType := "HTML"
body.SetContentType(&contentType) 
content := "Let's look for funding!"
body.SetContent(&content) 
	item.SetBody(body)
start := graphmodels.New()
dateTime := "2016-12-02T18:00:00"
start.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
start.SetTimeZone(&timeZone) 
	item.SetStart(start)
end := graphmodels.New()
dateTime := "2016-12-02T19:00:00"
end.SetDateTime(&dateTime) 
timeZone := "Pacific Standard Time"
end.SetTimeZone(&timeZone) 
	item.SetEnd(end)
	requestBody.SetItem(item)
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.Me().MessagesById("message-id").Attachments().Post(requestBody)


```