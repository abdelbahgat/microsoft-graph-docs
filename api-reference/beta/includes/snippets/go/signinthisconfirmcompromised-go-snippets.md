---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewConfirmCompromisedPostRequestBody()
requestIds := []String {
	"f01c6af6-6683-4a37-a945-0a925501eede",
	"42bf60ac-d0cb-4206-aa5c-101884298f55",
	"f09c8f14-8d8e-42cf-8a7e-732b0594e79b",

}
requestBody.SetRequestIds(requestIds)

graphClient.AuditLogs().SignIns().ConfirmCompromised().Post(requestBody)


```