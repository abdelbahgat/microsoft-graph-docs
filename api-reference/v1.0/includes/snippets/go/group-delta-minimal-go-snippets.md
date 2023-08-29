---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"Prefer": "return=minimal",
}
requestParameters := &graphconfig.DeltaRequestBuilderGetQueryParameters{
	Select: [] string {"displayName","description","mailNickname"},
}
configuration := &graphconfig.DeltaRequestBuilderGetRequestConfiguration{
	Headers: headers,
	QueryParameters: requestParameters,
}

result, err := graphClient.Groups().Delta()().GetWithRequestConfigurationAndResponseHandler(configuration, nil)


```