---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"User-Agent": "ContosoLOBApp/1.0",
}
configuration := &graphconfig.EvaluateApplicationRequestBuilderPostRequestConfiguration{
	Headers: headers,
}
requestBody := graphmodels.NewEvaluateApplicationPostRequestBody()
contentInfo := graphmodels.NewContentInfo()
"@odata.type" := "#microsoft.graph.contentInfo"
contentInfo.Set"@odata.type"(&"@odata.type") 
format := graphmodels.DEFAULT_CONTENTFORMAT 
contentInfo.SetFormat(&format) 
identifier := null
contentInfo.SetIdentifier(&identifier) 
state := graphmodels.REST_CONTENTSTATE 
contentInfo.SetState(&state) 


keyValuePair := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.keyValuePair"
keyValuePair.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_Enabled"
keyValuePair.SetName(&name) 
value := "True"
keyValuePair.SetValue(&value) 
keyValuePair1 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.keyValuePair"
keyValuePair1.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_Method"
keyValuePair1.SetName(&name) 
value := "Standard"
keyValuePair1.SetValue(&value) 
keyValuePair2 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.keyValuePair"
keyValuePair2.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_SetDate"
keyValuePair2.SetName(&name) 
value := "1/1/0001 12:00:00 AM"
keyValuePair2.SetValue(&value) 
keyValuePair3 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.keyValuePair"
keyValuePair3.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_SiteId"
keyValuePair3.SetName(&name) 
value := "cfa4cf1d-a337-4481-aa99-19d8f3d63f7c"
keyValuePair3.SetValue(&value) 
keyValuePair4 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.keyValuePair"
keyValuePair4.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_Name"
keyValuePair4.SetName(&name) 
value := "General"
keyValuePair4.SetValue(&value) 
keyValuePair5 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.keyValuePair"
keyValuePair5.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_ContentBits"
keyValuePair5.SetName(&name) 
value := "0"
keyValuePair5.SetValue(&value) 
keyValuePair6 := graphmodels.NewKeyValuePair()
"@odata.type" := "#microsoft.graph.keyValuePair"
keyValuePair6.Set"@odata.type"(&"@odata.type") 
name := "MSIP_Label_722a5300-ac39-4c9a-88e3-f54c46676417_ActionId"
keyValuePair6.SetName(&name) 
value := "00000000-0000-0000-0000-000000000000"
keyValuePair6.SetValue(&value) 

metadata := []graphmodels.KeyValuePairable {
	keyValuePair,
	keyValuePair1,
	keyValuePair2,
	keyValuePair3,
	keyValuePair4,
	keyValuePair5,
	keyValuePair6,

}
contentInfo.SetMetadata(metadata)
additionalData := map[string]interface{}{
	"format@odata.type" : "#microsoft.graph.contentFormat", 
	"state@odata.type" : "#microsoft.graph.contentState", 
	"metadata@odata.type" : "#Collection(microsoft.graph.keyValuePair)", 
}
contentInfo.SetAdditionalData(additionalData)
requestBody.SetContentInfo(contentInfo)
labelingOptions := graphmodels.NewLabelingOptions()
"@odata.type" := "#microsoft.graph.labelingOptions"
labelingOptions.Set"@odata.type"(&"@odata.type") 
assignmentMethod := graphmodels.STANDARD_ASSIGNMENTMETHOD 
labelingOptions.SetAssignmentMethod(&assignmentMethod) 
labelId := "97309856-9c28-4ac6-9382-5f8bc20c457b"
labelingOptions.SetLabelId(&labelId) 
downgradeJustification := null
labelingOptions.SetDowngradeJustification(&downgradeJustification) 
extendedProperties := []graphmodels.KeyValuePairable {

}
labelingOptions.SetExtendedProperties(extendedProperties)
additionalData := map[string]interface{}{
	"assignmentMethod@odata.type" : "#microsoft.graph.assignmentMethod", 
	"labelId@odata.type" : "#Guid", 
	"extendedProperties@odata.type" : "#Collection(microsoft.graph.keyValuePair)", 
}
labelingOptions.SetAdditionalData(additionalData)
requestBody.SetLabelingOptions(labelingOptions)

result, err := graphClient.InformationProtection().Policy().Labels().EvaluateApplication().PostWithRequestConfigurationAndResponseHandler(requestBody, configuration, nil)


```