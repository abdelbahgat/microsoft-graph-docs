---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestParameters := &graphconfig.InstancesRequestBuilderGetQueryParameters{
	StartDateTime: "2019-04-08T09:00:00.0000000",
	EndDateTime: "2019-04-30T09:00:00.0000000",
	Select: [] string {"subject","bodyPreview","seriesMasterId","type","recurrence","start","end"},
}
configuration := &graphconfig.InstancesRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

result, err := graphClient.Me().EventsById("event-id").Instances().GetWithRequestConfigurationAndResponseHandler(configuration, nil)


```