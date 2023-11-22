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


requestParameters := &graphidentitygovernance.IdentityGovernanceLifecycleWorkflowsWorkflowItemRunItemTaskProcessingResultsRequestBuilderGetQueryParameters{
	Select: [] string {"id","failureReason","processingStatus","subject"},
}
configuration := &graphidentitygovernance.IdentityGovernanceLifecycleWorkflowsWorkflowItemRunItemTaskProcessingResultsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

taskProcessingResults, err := graphClient.IdentityGovernance().LifecycleWorkflows().Workflows().ByWorkflowId("workflow-id").Runs().ByRunId("run-id").TaskProcessingResults().Get(context.Background(), configuration)


```