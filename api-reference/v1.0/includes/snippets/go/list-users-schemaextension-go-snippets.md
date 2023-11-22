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


requestParameters := &graphusers.UsersRequestBuilderGetQueryParameters{
	Select: [] string {"ext55gb1l09_msLearnCourses"},
}
configuration := &graphusers.UsersRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

users, err := graphClient.Users().Get(context.Background(), configuration)


```