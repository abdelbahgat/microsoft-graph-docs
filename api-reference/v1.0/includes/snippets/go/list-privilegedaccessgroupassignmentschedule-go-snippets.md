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



requestFilter := "groupId eq '2b5ed229-4072-478d-9504-a047ebd4b07d' and principalId eq '3cce9d87-3986-4f19-8335-7ed075408ca2'"

requestParameters := &graphidentitygovernance.IdentityGovernancePrivilegedAccessGroupAssignmentSchedulesRequestBuilderGetQueryParameters{
	Filter: &requestFilter,
}
configuration := &graphidentitygovernance.IdentityGovernancePrivilegedAccessGroupAssignmentSchedulesRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

assignmentSchedules, err := graphClient.IdentityGovernance().PrivilegedAccess().Group().AssignmentSchedules().Get(context.Background(), configuration)


```