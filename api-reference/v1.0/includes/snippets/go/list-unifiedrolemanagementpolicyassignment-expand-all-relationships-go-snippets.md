---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestParameters := &graphconfig.RoleManagementPolicyAssignmentsRequestBuilderGetQueryParameters{
	Filter: "scopeId eq '/' and scopeType eq 'DirectoryRole' and roleDefinitionId eq '62e90394-69f5-4237-9190-012177145e10'",
	Expand: [] string {"policy($expand=rules)"},
}
configuration := &graphconfig.RoleManagementPolicyAssignmentsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

result, err := graphClient.Policies().RoleManagementPolicyAssignments().GetWithRequestConfigurationAndResponseHandler(configuration, nil)


```