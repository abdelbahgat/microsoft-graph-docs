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



accessPackageAssignmentResourceRoles, err := graphClient.IdentityGovernance().EntitlementManagement().AccessPackageAssignmentResourceRoles().Get(context.Background(), nil)


```