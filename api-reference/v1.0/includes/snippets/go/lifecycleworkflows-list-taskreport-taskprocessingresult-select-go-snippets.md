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


requestParameters := &graphidentitygovernance.IdentityGovernanceLifecycleWorkflowsWorkflowItemTaskReportItemTaskProcessingResultsRequestBuilderGetQueryParameters{
	Select: [] string {"id","failureReason","processingStatus","subject","task"},
}
configuration := &graphidentitygovernance.IdentityGovernanceLifecycleWorkflowsWorkflowItemTaskReportItemTaskProcessingResultsRequestBuilderGetRequestConfiguration{
	QueryParameters: requestParameters,
}

taskProcessingResults, err := graphClient.IdentityGovernance().LifecycleWorkflows().Workflows().ByWorkflowId("workflow-id").TaskReports().ByTaskReportId("taskReport-id").TaskProcessingResults().Get(context.Background(), configuration)


```