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



role := "{role}"
getByUserRole, err := graphClient.Solutions().VirtualEvents().Webinars().GetByUserRoleWithRole(&role).Get(context.Background(), nil)


```