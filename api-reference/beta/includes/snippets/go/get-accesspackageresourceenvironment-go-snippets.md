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



accessPackageResourceEnvironments, err := graphClient.IdentityGovernance().EntitlementManagement().AccessPackageResourceEnvironments().ByAccessPackageResourceEnvironmentId("accessPackageResourceEnvironment-id").Get(context.Background(), nil)


```