---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAuthoredNote()
content := graphmodels.NewItemBody()
content := "String"
content.SetContent(&content) 
contentType := graphmodels.TEXT_BODYTYPE 
content.SetContentType(&contentType) 
requestBody.SetContent(content)

result, err := graphClient.Privacy().SubjectRightsRequestsById("subjectRightsRequest-id").Notes().Post(requestBody)


```