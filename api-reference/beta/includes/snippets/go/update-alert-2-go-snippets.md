---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"Prefer": "return=representation",
}
configuration := &graphconfig.AlertRequestBuilderPatchRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewAlert()
assignedTo := "String"
requestBody.SetAssignedTo(&assignedTo) 
closedDateTime , err := time.Parse(time.RFC3339, "String (timestamp)")
requestBody.SetClosedDateTime(&closedDateTime) 
comments := []String {
	"String",

}
requestBody.SetComments(comments)
feedback := graphmodels.ALERTFEEDBACK_GRAPH_TYPE: MICROSOFT_@ODATA_ALERTFEEDBACK 
requestBody.SetFeedback(&feedback) 
status := graphmodels.ALERTSTATUS_GRAPH_TYPE: MICROSOFT_@ODATA_ALERTSTATUS 
requestBody.SetStatus(&status) 
tags := []String {
	"String",

}
requestBody.SetTags(tags)
vendorInformation := graphmodels.NewSecurityVendorInformation()
provider := "String"
vendorInformation.SetProvider(&provider) 
vendor := "String"
vendorInformation.SetVendor(&vendor) 
requestBody.SetVendorInformation(vendorInformation)

graphClient.Security().AlertsById("alert-id").PatchWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```