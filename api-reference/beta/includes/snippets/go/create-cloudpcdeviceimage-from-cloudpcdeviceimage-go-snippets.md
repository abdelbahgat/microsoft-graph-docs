---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewCloudPcDeviceImage()
"@odata.type" := "#microsoft.graph.cloudPcDeviceImage"
requestBody.Set"@odata.type"(&"@odata.type") 
displayName := "Display Name value"
requestBody.SetDisplayName(&displayName) 
osBuildNumber := "OS Build Number value"
requestBody.SetOsBuildNumber(&osBuildNumber) 
operatingSystem := "Operating System value"
requestBody.SetOperatingSystem(&operatingSystem) 
version := "Version value"
requestBody.SetVersion(&version) 
sourceImageResourceId := "/subscriptions/0ac520ee-14c0-480f-b6c9-0a90c58ffff/resourceGroups/Example/providers/Microsoft.Compute/images/exampleImage"
requestBody.SetSourceImageResourceId(&sourceImageResourceId) 

result, err := graphClient.DeviceManagement().VirtualEndpoint().DeviceImages().Post(requestBody)


```