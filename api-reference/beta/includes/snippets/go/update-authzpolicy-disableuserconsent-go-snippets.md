---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestBody := graphmodels.NewAuthorizationPolicy()
permissionGrantPolicyIdsAssignedToDefaultUserRole := []string {

}
requestBody.SetPermissionGrantPolicyIdsAssignedToDefaultUserRole(permissionGrantPolicyIdsAssignedToDefaultUserRole)

graphClient.Policies().AuthorizationPolicyById("authorizationPolicy-id").Patch(requestBody)


```