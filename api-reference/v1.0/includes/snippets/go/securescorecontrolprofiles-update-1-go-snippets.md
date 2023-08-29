---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewSecureScoreControlProfile()
vendorInformation := graphmodels.NewSecurityVendorInformation()
provider := "SecureScore"
vendorInformation.SetProvider(&provider) 
providerVersion := null
vendorInformation.SetProviderVersion(&providerVersion) 
subProvider := null
vendorInformation.SetSubProvider(&subProvider) 
vendor := "Microsoft"
vendorInformation.SetVendor(&vendor) 
requestBody.SetVendorInformation(vendorInformation)
additionalData := map[string]interface{}{
	"assignedTo" : "", 
	"comment" : "control is reviewed", 
	"state" : "Reviewed", 
}
requestBody.SetAdditionalData(additionalData)

graphClient.Security().SecureScoreControlProfilesById("secureScoreControlProfile-id").Patch(requestBody)


```