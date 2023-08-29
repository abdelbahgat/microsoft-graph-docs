---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewPersonAnnotation()
detail := graphmodels.NewItemBody()
contentType := graphmodels.TEXT_BODYTYPE 
detail.SetContentType(&contentType) 
content := "I am originally from Australia, but grew up in Moscow, Russia."
detail.SetContent(&content) 
requestBody.SetDetail(detail)
displayName := "About Me"
requestBody.SetDisplayName(&displayName) 

result, err := graphClient.Me().Profile().Notes().Post(requestBody)


```