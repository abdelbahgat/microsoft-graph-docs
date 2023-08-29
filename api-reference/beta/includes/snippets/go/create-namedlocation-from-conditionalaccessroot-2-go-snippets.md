---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewNamedLocation()
"@odata.type" := "#microsoft.graph.countryNamedLocation"
requestBody.Set"@odata.type"(&"@odata.type") 
displayName := "Named location with unknown countries and regions"
requestBody.SetDisplayName(&displayName) 
additionalData := map[string]interface{}{
	countriesAndRegions := []String {
		"US",
		"GB",

	}
	includeUnknownCountriesAndRegions := true
requestBody.SetIncludeUnknownCountriesAndRegions(&includeUnknownCountriesAndRegions) 
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.Identity().ConditionalAccess().NamedLocations().Post(requestBody)


```