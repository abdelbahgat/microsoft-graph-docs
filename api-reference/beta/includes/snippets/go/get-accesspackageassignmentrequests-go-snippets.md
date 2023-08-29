---
description: "Automatically generated file. DO NOT MODIFY"
---

```go

//THE GO SDK IS IN PREVIEW. NON-PRODUCTION USE ONLY
graphClient := msgraphsdk.NewGraphServiceClient(requestAdapter)

requestParameters := &graphconfig.AccessPackageAssignmentRequestsRequestBuilderGetQueryParameters{
	Expand: [] string {"requestor($expand=connectedOrganization)"},
	Filter: "(requestState eq 'PendingApproval')",
}
configuration := &graphconfig.AccessPackageAssignmentRequestsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

result, err := graphClient.IdentityGovernance().EntitlementManagement().AccessPackageAssignmentRequests().GetWithRequestConfigurationAndResponseHandler(configuration, nil)


```