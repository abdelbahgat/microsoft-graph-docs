---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphusers "github.com/microsoftgraph/msgraph-beta-sdk-go/users"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



requestFilter := "resourceId eq 8e881353-1735-45af-af21-ee1344582a4d"

requestParameters := &graphusers.UserItemAppRoleAssignmentsRequestBuilderGetQueryParameters{
	Filter: &requestFilter,
}
configuration := &graphusers.UserItemAppRoleAssignmentsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

appRoleAssignments, err := graphClient.Users().ByUserId("user-id").AppRoleAssignments().Get(context.Background(), configuration)


```