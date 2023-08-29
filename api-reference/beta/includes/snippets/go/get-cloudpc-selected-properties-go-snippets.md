---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestParameters := &graphconfig.CloudPCRequestBuilderGetQueryParameters{
	Select: [] string {"id","displayName","imageDisplayName","lastModifiedDateTime","lastRemoteActionResult","lastLoginResult"},
}
configuration := &graphconfig.CloudPCRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

result, err := graphClient.DeviceManagement().VirtualEndpoint().CloudPCsById("cloudPC-id").GetWithRequestConfigurationAndResponseHandler(configuration, nil)


```