---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)



graphClient.RoleManagement().Directory().RoleEligibilityScheduleRequests().ByUnifiedRoleEligibilityScheduleRequestId("unifiedRoleEligibilityScheduleRequest-id").Cancel().Post(context.Background(), nil)


```