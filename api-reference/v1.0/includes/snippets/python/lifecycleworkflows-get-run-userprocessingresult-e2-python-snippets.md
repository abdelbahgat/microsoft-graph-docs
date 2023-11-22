---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = UserProcessingResultItemRequestBuilder.UserProcessingResultItemRequestBuilderGetQueryParameters(
		select = ["id","failedTasksCount","processingStatus","totalTasksCount","totalUnprocessedTasksCount","subject"],
)

request_configuration = UserProcessingResultItemRequestBuilder.UserProcessingResultItemRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.identity_governance.lifecycle_workflows.workflows.by_workflow_id('workflow-id').runs.by_run_id('run-id').user_processing_results.by_user_processing_result_id('userProcessingResult-id').get(request_configuration = request_configuration)


```