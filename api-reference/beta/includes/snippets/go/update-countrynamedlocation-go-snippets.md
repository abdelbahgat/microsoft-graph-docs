---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewNamedLocation()
"@odata.type" := "#microsoft.graph.countryNamedLocation"
requestBody.Set"@odata.type"(&"@odata.type") 
displayName := "Updated named location without unknown countries and regions"
requestBody.SetDisplayName(&displayName) 
additionalData := map[string]interface{}{
	countriesAndRegions := []String {
		"CA",
		"IN",

	}
	includeUnknownCountriesAndRegions := false
requestBody.SetIncludeUnknownCountriesAndRegions(&includeUnknownCountriesAndRegions) 
}
requestBody.SetAdditionalData(additionalData)

graphClient.Identity().ConditionalAccess().NamedLocationsById("namedLocation-id").Patch(requestBody)


```