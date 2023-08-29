---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"ConsistencyLevel": "eventual",
}
requestParameters := &graphconfig.MeRequestBuilderGetQueryParameters{
	Expand: [] string {"manager($levels=max;$select=id,displayName)"},
	Select: [] string {"id","displayName"},
	Count: true,
}
configuration := &graphconfig.MeRequestBuilderGetRequestConfiguration{
	Headers: headers,
	QueryParameters: requestParameters,
}

result, err := graphClient.Me().GetWithRequestConfigurationAndResponseHandler(configuration, nil)


```