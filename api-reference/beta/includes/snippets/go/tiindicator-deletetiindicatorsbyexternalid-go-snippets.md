---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewDeleteTiIndicatorsByExternalIdPostRequestBody()
value := []String {
	"externalId-value1",
	"externalId-value2",

}
requestBody.SetValue(value)

result, err := graphClient.Security().TiIndicators().DeleteTiIndicatorsByExternalId().Post(requestBody)


```