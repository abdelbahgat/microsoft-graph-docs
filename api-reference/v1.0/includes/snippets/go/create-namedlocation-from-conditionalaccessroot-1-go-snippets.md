---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewNamedLocation()
"@odata.type" := "#microsoft.graph.ipNamedLocation"
requestBody.Set"@odata.type"(&"@odata.type") 
displayName := "Untrusted IP named location"
requestBody.SetDisplayName(&displayName) 
additionalData := map[string]interface{}{
	isTrusted := false
requestBody.SetIsTrusted(&isTrusted) 


 := graphmodels.New()
"@odata.type" := "#microsoft.graph.iPv4CidrRange"
.Set"@odata.type"(&"@odata.type") 
cidrAddress := "12.34.221.11/22"
.SetCidrAddress(&cidrAddress) 
 := graphmodels.New()
"@odata.type" := "#microsoft.graph.iPv6CidrRange"
.Set"@odata.type"(&"@odata.type") 
cidrAddress := "2001:0:9d38:90d6:0:0:0:0/63"
.SetCidrAddress(&cidrAddress) 

	ipRanges := []graphmodels.Objectable {
		,
		,

	}
}
requestBody.SetAdditionalData(additionalData)

result, err := graphClient.Identity().ConditionalAccess().NamedLocations().Post(requestBody)


```