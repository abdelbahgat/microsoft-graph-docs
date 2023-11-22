---
description: "Automatically generated file. DO NOT MODIFY"
---

```python

# THE PYTHON SDK IS IN PREVIEW. FOR NON-PRODUCTION USE ONLY

graph_client = GraphServiceClient(credentials, scopes)

query_params = VersionsRequestBuilder.VersionsRequestBuilderGetQueryParameters(
		select = ["category","displayName","versionNumber"],
)

request_configuration = VersionsRequestBuilder.VersionsRequestBuilderGetRequestConfiguration(
query_parameters = query_params,
)

result = await graph_client.identity_governance.lifecycle_workflows.workflows.by_workflow_id('workflow-id').versions.get(request_configuration = request_configuration)


```