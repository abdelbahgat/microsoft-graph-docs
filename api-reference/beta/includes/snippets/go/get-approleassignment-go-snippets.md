---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



appRoleAssignments, err := graphClient.Me().AppRoleAssignments().ByAppRoleAssignmentId("appRoleAssignment-id").Get(context.Background(), nil)


```