---
description: "Automatically generated file. DO NOT MODIFY"
---

```go


import (
	  "context"
	  abstractions "github.com/microsoft/kiota-abstractions-go"
	  msgraphsdk "github.com/microsoftgraph/msgraph-beta-sdk-go"
	  graphrolemanagement "github.com/microsoftgraph/msgraph-beta-sdk-go/rolemanagement"
	  //other-imports
)

graphClient := msgraphsdk.NewGraphServiceClientWithCredentials(cred, scopes)


headers := abstractions.NewRequestHeaders()
headers.Add("ConsistencyLevel", "eventual")


requestCount := true
requestFilter := "principalId eq '2c7936bc-3517-40f3-8eda-4806637b6516' and roleDefinitionId eq 'fe930be7-5e62-47db-91af-98c3a49a38b1'"

requestParameters := &graphrolemanagement.RoleManagementDirectoryTransitiveRoleAssignmentsRequestBuilderGetQueryParameters{
	Count: &requestCount,
	Filter: &requestFilter,
}
configuration := &graphrolemanagement.RoleManagementDirectoryTransitiveRoleAssignmentsRequestBuilderGetRequestConfiguration{
	Headers: headers,
	QueryParameters: requestParameters,
}

transitiveRoleAssignments, err := graphClient.RoleManagement().Directory().TransitiveRoleAssignments().Get(context.Background(), configuration)


```