---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewDomain()
isDefault := true
requestBody.SetIsDefault(&isDefault) 
supportedServices := []String {
	"Email",
	"OfficeCommunicationsOnline",

}
requestBody.SetSupportedServices(supportedServices)

graphClient.DomainsById("domain-id").Patch(requestBody)


```