---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  msgraphsdk "github.com/microsoftgraph/msgraph-sdk-go"
	  graphidentitygovernance "github.com/microsoftgraph/msgraph-sdk-go/identitygovernance"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


requestParameters := &graphidentitygovernance.IdentityGovernanceEntitlementManagementAssignmentsAdditionalAccess(accessPackageId='{accessPackageId}',incompatibleAccessPackageId='{incompatibleAccessPackageId}')RequestBuilderGetQueryParameters{
	Expand: [] string {"target"},
}
configuration := &graphidentitygovernance.IdentityGovernanceEntitlementManagementAssignmentsAdditionalAccess(accessPackageId='{accessPackageId}',incompatibleAccessPackageId='{incompatibleAccessPackageId}')RequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

accessPackageId := "{accessPackageId}"
incompatibleAccessPackageId := "{incompatibleAccessPackageId}"
additionalAccess, err := graphClient.IdentityGovernance().EntitlementManagement().Assignments().AdditionalAccessWithAccessPackageIdWithIncompatibleAccessPackageId(&accessPackageId, &incompatibleAccessPackageId).Get(context.Background(), configuration)


```