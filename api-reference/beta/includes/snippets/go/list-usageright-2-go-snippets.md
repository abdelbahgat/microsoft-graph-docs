---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestParameters := &msgraphsdk.UsageRightsRequestBuilderGetQueryParameters{
	Filter: "state%20in%20('active',%20'suspended')%20and%20serviceIdentifier%20in%20('ABCD')",
}
options := &msgraphsdk.UsageRightsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}
deviceId := "device-id"
result, err := graphClient.DevicesById(&deviceId).UsageRights().GetWithRequestConfigurationAndResponseHandler(options, nil)


```