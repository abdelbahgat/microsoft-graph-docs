---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphmodels "github.com/microsoftgraph/msgraph-sdk-go/models"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestBody := graphmodels.NewAuthorizationPolicy()
defaultUserRolePermissions := graphmodels.NewDefaultUserRolePermissions()
permissionGrantPoliciesAssigned := []string {
	"managePermissionGrantsForSelf.microsoft-user-default-low",
}
defaultUserRolePermissions.SetPermissionGrantPoliciesAssigned(permissionGrantPoliciesAssigned)
requestBody.SetDefaultUserRolePermissions(defaultUserRolePermissions)

authorizationPolicy, err := graphClient.Policies().AuthorizationPolicy().Patch(context.Background(), requestBody, nil)


```