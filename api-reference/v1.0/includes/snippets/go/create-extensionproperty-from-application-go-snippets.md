---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewExtensionProperty()
name := "jobGroup"
requestBody.SetName(&name) 
dataType := "String"
requestBody.SetDataType(&dataType) 
targetObjects := []String {
	"User",

}
requestBody.SetTargetObjects(targetObjects)

result, err := graphClient.ApplicationsById("application-id").ExtensionProperties().Post(requestBody)


```