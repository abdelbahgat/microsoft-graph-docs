---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewFavoritePostRequestBody()
messageIds := []String {
	"MC172851",
	"MC167983",

}
requestBody.SetMessageIds(messageIds)

result, err := graphClient.Admin().ServiceAnnouncement().Messages().Favorite().Post(requestBody)


```