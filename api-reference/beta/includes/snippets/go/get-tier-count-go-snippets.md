---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  abstractions "github.com/microsoft/kiota-abstractions-go"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphgroups "github.com/microsoftgraph/msgraph-beta-sdk-go/groups"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


headers := abstractions.NewRequestHeaders()
headers.Add("ConsistencyLevel", "eventual")


requestCount := true
requestSearch := "\"displayName:tier\""

requestParameters := &graphgroups.GroupItemTransitiveMembersGraph.userRequestBuilderGetQueryParameters{
	Count: &requestCount,
	Orderby: [] string {"displayName"},
	Search: &requestSearch,
	Select: [] string {"displayName","id"},
}
configuration := &graphgroups.GroupItemTransitiveMembersGraph.userRequestBuilderGetRequestConfiguration{
	Headers: headers,
	QueryParameters: requestParameters,
}

graphUser, err := graphClient.Groups().ByGroupId("group-id").TransitiveMembers().GraphUser().Get(context.Background(), configuration)


```