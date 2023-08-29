---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAudioRoutingGroup()
id := "oneToOne"
requestBody.SetId(&id) 
routingMode := graphmodels.ONETOONE_ROUTINGMODE 
requestBody.SetRoutingMode(&routingMode) 
sources := []String {
	"632899f8-2ea1-4604-8413-27bd2892079f",

}
requestBody.SetSources(sources)
receivers := []String {
	"550fae72-d251-43ec-868c-373732c2704f",

}
requestBody.SetReceivers(receivers)

result, err := graphClient.Communications().CallsById("call-id").AudioRoutingGroups().Post(requestBody)


```