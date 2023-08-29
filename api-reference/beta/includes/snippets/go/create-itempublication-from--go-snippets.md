---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewItemPublication()
description := "One persons journey to the top of the branding management field."
requestBody.SetDescription(&description) 
displayName := "Got Brands? The story of Innocenty Popov and his journey to the top."
requestBody.SetDisplayName(&displayName) 
publishedDate := "Date"
requestBody.SetPublishedDate(&publishedDate) 
publisher := "International Association of Branding Management Publishing"
requestBody.SetPublisher(&publisher) 
thumbnailUrl := "https://iabm.io/sdhdfhsdhshsd.jpg"
requestBody.SetThumbnailUrl(&thumbnailUrl) 
webUrl := "https://www.iabm.io"
requestBody.SetWebUrl(&webUrl) 

result, err := graphClient.Me().Profile().Publications().Post(requestBody)


```