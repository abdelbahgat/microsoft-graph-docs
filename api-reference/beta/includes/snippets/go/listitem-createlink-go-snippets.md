---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewCreateLinkPostRequestBody()
type := "embed"
requestBody.SetType(&type) 

result, err := graphClient.SitesById("site-id").ListsById("list-id").ItemsById("listItem-id").CreateLink(site-id, list-id, listItem-id).Post(requestBody)


```