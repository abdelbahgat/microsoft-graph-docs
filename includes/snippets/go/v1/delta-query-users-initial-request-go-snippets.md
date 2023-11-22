---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphusers "github.com/microsoftgraph/msgraph-sdk-go/users"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphusers.UsersDelta()RequestBuilderGetQueryParameters{
	Select: [] string {"displayName","givenName","surname"},
}
configuration := &graphusers.UsersDelta()RequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

delta, err := graphClient.Users().Delta().Get(context.Background(), configuration)


```