---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAssociateWithHubSitesPostRequestBody()
hubSiteUrls := []String {
	"https://graph.microsoft.com/v1.0/sites/{site-id}",

}
requestBody.SetHubSiteUrls(hubSiteUrls)
propagateToExistingLists := false
requestBody.SetPropagateToExistingLists(&propagateToExistingLists) 

graphClient.SitesById("site-id").ContentTypesById("contentType-id").AssociateWithHubSites(site-id, contentType-id).Post(requestBody)


```