---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

headers := map[string]string{
	"Prefer": "outlook.timezone=\"Pacific Standard Time\"",
}
configuration := &graphconfig.OutlookTaskRequestBuilderGetRequestConfiguration{
	Headers: headers,
}

result, err := graphClient.Me().Outlook().TasksById("outlookTask-id").GetWithRequestConfigurationAndResponseHandler(configuration, nil)


```