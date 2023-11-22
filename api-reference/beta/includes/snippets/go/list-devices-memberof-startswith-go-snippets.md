---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  abstractions "github.com/microsoft/kiota-abstractions-go"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphdevices "github.com/microsoftgraph/msgraph-beta-sdk-go/devices"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


headers := abstractions.NewRequestHeaders()
headers.Add("ConsistencyLevel", "eventual")


requestCount := true
requestFilter := "startswith(displayName, 'A')"

requestParameters := &graphdevices.DeviceItemMemberOfGraph.groupRequestBuilderGetQueryParameters{
	Count: &requestCount,
	Orderby: [] string {"displayName"},
	Filter: &requestFilter,
}
configuration := &graphdevices.DeviceItemMemberOfGraph.groupRequestBuilderGetRequestConfiguration{
	Headers: headers,
	QueryParameters: requestParameters,
}

graphGroup, err := graphClient.Devices().ByDeviceId("device-id").MemberOf().GraphGroup().Get(context.Background(), configuration)


```